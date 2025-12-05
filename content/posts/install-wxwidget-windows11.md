---
date: '2025-12-05T14:06:08+01:00'
draft: false
title: 'Installare wxWidget su Windows 11'
categories: [tutorials]
tags: [wxwidget]
cover:
  image: images/wxWidget-windows.png
  hiddenInList: false
---


*Una guida passo passo e diretta su come installare una delle librerie multipiattaforma per GUI più popolari su ambiente Windows.*

---

## Installare wxWidgets su windows 11 con vcpkg per msvc

*testato su Windows 11.*

## Guida passo dopo passo

Se state leggendo questa guida sicuramente saprete cos'è wxWidget nello specifico, quindi non mi perderò in spiegazioni inutili.

Andiamo dritto al sodo:

1. Inanzittutto dovrai creare una cartella dove poter inserita la libreria, per convenzione la chiamerò 'dev'.
2. Ora dovrai clonare la repo github di vcpkg

*vcpkg è un sistema di gestione pacchetti per librerie open source gestita e mantenuta da Microsoft e dalla community C++.*

Apri il Terminale o Powershell, assicurati di lavorare nella cartella 'dev' appena creata dopodichè, digita i seguenti comandi:

> git clone <https://github.com/Microsoft/vcpkg.git>
> cd vcpkg
> .\bootstrap-vcpkg.bat
> .\vcpkg integrate install

## Installare la libreria wxWidgets nella versione per il compilatore MSVC

In questo caso il comando seguente installerà la versione statica della libreria, ma tu sei libero ovviamente di installare la versione dinamica...
> .\vcpkg install wxwidgets:x64-windows-static

## Aggiungere ai CMake options wxWidgets

In Clion o altro IDE, aggiungi ai CMake options i seguenti argomenti:

> -DCMAKE_TOOLCHAIN_FILE=C:/dev/vcpkg/scripts/buildsystems/vcpkg.cmake
> -DVCPKG_TARGET_TRIPLET=x64-windows-static

Adesso non ci resta di creare un progetto CMake e configurare il CMakeLists.txt.

> CMakeLists.txt

```cmake
cmake_minimum_required(VERSION 3.25)
project(wxtest LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 23)

// MT per compilazione statica
set(CMAKE_MSVC_RUNTIME_LIBRARY "MultiThreaded$<$<CONFIG:Debug>:Debug>")

find_package(wxWidgets CONFIG REQUIRED)

add_executable(wxtest WIN32 main.cpp)

target_link_libraries(wxtest PRIVATE wx::core wx::base)

target_compile_options(wxtest PRIVATE
        /MT
)
// Opzionale
target_link_options(wxtest PRIVATE
        /LTCG
        /OPT:REF
        /OPT:ICF
)
```

Ora nel file main.cpp scriviamo questo codice esempio:

```cpp
// wxWidgets "Hello World" Program
 
// For compilers that support precompilation, includes "wx/wx.h".
#include <wx/wxprec.h>
 
#ifndef WX_PRECOMP
    #include <wx/wx.h>
#endif
 
class MyApp : public wxApp
{
public:
    virtual bool OnInit();
};
 
class MyFrame : public wxFrame
{
public:
    MyFrame();
 
private:
    void OnHello(wxCommandEvent& event);
    void OnExit(wxCommandEvent& event);
    void OnAbout(wxCommandEvent& event);
};
 
enum
{
    ID_Hello = 1
};
 
wxIMPLEMENT_APP(MyApp);
 
bool MyApp::OnInit()
{
    MyFrame *frame = new MyFrame();
    frame->Show(true);
    return true;
}
 
MyFrame::MyFrame()
    : wxFrame(NULL, wxID_ANY, "Hello World")
{
    wxMenu *menuFile = new wxMenu;
    menuFile->Append(ID_Hello, "&Hello...\tCtrl-H",
                     "Help string shown in status bar for this menu item");
    menuFile->AppendSeparator();
    menuFile->Append(wxID_EXIT);
 
    wxMenu *menuHelp = new wxMenu;
    menuHelp->Append(wxID_ABOUT);
 
    wxMenuBar *menuBar = new wxMenuBar;
    menuBar->Append(menuFile, "&File");
    menuBar->Append(menuHelp, "&Help");
 
    SetMenuBar( menuBar );
 
    CreateStatusBar();
    SetStatusText("Welcome to wxWidgets!");
 
    Bind(wxEVT_MENU, &MyFrame::OnHello, this, ID_Hello);
    Bind(wxEVT_MENU, &MyFrame::OnAbout, this, wxID_ABOUT);
    Bind(wxEVT_MENU, &MyFrame::OnExit, this, wxID_EXIT);
}
 
void MyFrame::OnExit(wxCommandEvent& event)
{
    Close(true);
}
 
void MyFrame::OnAbout(wxCommandEvent& event)
{
    wxMessageBox("This is a wxWidgets Hello World example",
                 "About Hello World", wxOK | wxICON_INFORMATION);
}
 
void MyFrame::OnHello(wxCommandEvent& event)
{
    wxLogMessage("Hello world from wxWidgets!");
}
```

Se tutto è stato eseguito correttamente, dovrai vedere la tua prima finestra creata con la libreria wxWidget, adesso non ti resta che testare tutte le sue funzionalità!
