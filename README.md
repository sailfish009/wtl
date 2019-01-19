//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

    Installation:

    1. git clone https://github.com/sailfish009/wtl
    
    2. copy include directory to other place to easy to remember ( EX): C:\WTL\include)
    
    3. try to build WTLExplorer(wtl\Samples\WTLExplorer) with your visual studio ide.
    
       // try to change below macros to your windows os version
       stdafx.h:
       #define WINVER		0x0A00
       #define _WIN32_IE	0x0A00
       #define _RICHEDIT_VER	0x0100
       #define NTDDI_VERSION 0x06030000
       #define _WIN32_WINNT  0x0A00

    4. Properties -> General -> Target Platform (win8.1 -> Windows 10)

    5. Properties -> VC++ Directories -> Include Directories
    
       // try to change directories match with your ide environment (mine win10, vs2017 pro)
       C:\WTL\Include
       C:\Program Files (x86)\Windows Kits\10\Include\10.0.17763.0\um
       C:\Program Files (x86)\Windows Kits\10\Include\10.0.17763.0\ucrt
       C:\Program Files (x86)\Windows Kits\10\Include\10.0.17763.0\shared
       
    6. try to build WTLExplorer and see if it built fine and run.

    NOTE:

    // WTL9 works fine with vs2017 express (with WDK 7.1) or professional 

    // add following 2 lines to your project source code
    
    // add WTL/include to your project directory (no need to run setup.js)

    #pragma comment(lib, "legacy_stdio_definitions.lib")

    #pragma comment(lib, "atlthunk.lib")


//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////


Windows Template Library - WTL Version 9.1            (build 5321 final) 2015-11-17

Copyright © 2015 Microsoft Corporation, WTL Team. All rights reserved.
 
This file is a part of the Windows Template Library.
The use and distribution terms for this software are covered by the
Microsoft Public License (http://opensource.org/licenses/MS-PL)
which can be found in the file MS-PL.txt at the root folder.
 
 
Welcome to the Windows Template Library, version 9.1. This document contains the following topics:
 
Introduction
Features and Installation
Packing List
Class Overview
ATL/WTL AppWizard
Support for Windows CE
Support for Visual C++ Express
Notes
Changes Between WTL 9.1 and 9.0
Changes Between WTL 9.0 and 8.0
Changes Between WTL 8.0 and 7.5
Changes Between WTL 7.5 and 7.1
Changes Between WTL 7.1 and 7.0
Changes Between WTL 7.0 and 3.1
Changes Between WTL 3.1 and 3.0
 
 
Introduction
 
Windows Template Library, or WTL, is a set of classes that extend ATL to support more complex user interfaces for either applications or various UI components, while maintaining the big advantage of ATL - small and fast code. WTL classes were designed to be the best and the easiest way to implement rich Win32 based UI for ATL based applications, servers, components, and controls.
 
WTL provides support for implementing many user interface elements, from frame and popup windows, to MDI, standard and common controls, common dialogs, property sheets and pages, GDI objects, UI updating, scrollable windows, splitter windows, command bars, etc. The WTL classes are mostly templated and use minimal instance data and inline functions. They were not designed as a framework, so they do not force a particular application model, and can accommodate any. The classes do not use hooks or thread local storage, so they have no restrictions that those techniques impose. They also have no inter-dependencies and can be freely mixed with straight SDK code. In summary, WTL delivers very small and efficient code, very close in size and speed to SDK programs, while presenting a more logical, object oriented model to a programmer.
 
 
Features and Installation
 
This is the eigth public release of WTL, after WTL 3.0, 3.1, 7.0, 7.1, 7.5, 8.0, and 9.0. This version is released under the Microsoft Public License, enabling developers from the WTL community to contribute to the library.
 
WTL classes can be used with either VC++ 6.0, VC++ .NET 2002 or 2003, VC++ 2005 or 2008 or 2010 or 2012 or 2013 or 2015, or EVC++ 4.0 or 3.0. AppWizard for Visual Studio is included.
 
The WTL classes are provided in header files located in the include directory. The only header files that must be included is atlapp.h, while others can be used when needed. The name of the file doesn't mean that you have to create an application, just that atlapp.h contains base definitions required for WTL projects.
 
To install WTL, just copy the whole directory structure, or unpack the archive file, to the location of your choice. Please be sure to add the WTL\include directory to the list of include directories in VC++, so that the compiler can find them when you include them in your projects..
 
Setup programs for the AppWizard are provided. After executing the setup script, ATL/WTL AppWizard will appear in the list of AppWizards when you select File.New.Project in VC++ IDE. The file AppWiz\setup.js is the setup script for all supported versions of Visual Studio, while AppWizards for Windows CE have separate scripts for VS2005 and VS2008 SmartDevice projects.
 
To manually install AppWizard for VC++ .NET 2002/2003, copy all WTLAppWiz.* files from AppWiz\Files to VC++ .NET projects directory, %VC7DIR%\Vc7\vcprojects, where %VC7DIR% is the directory where VC++ .NET 2002/2003 is installed. After that, open WTLAppWiz.vsz and modify the like that contains ABSOLUTE_PATH to contain %WTLDIR%\AppWiz\Files, where %WTLDIR% is the directory where WTL files are.
 
Platform support and requirements:
 
    Compiler/IDE/ATL:
            Visual C++ 6.0   (ATL 3.0)
            Visual C++.NET 2002   (ATL 7.0)
            Visual C++.NET 2003   (ATL 7.1)
            Visual C++ 2005   (ATL 8.0)
            Visual C++ 2008   (ATL 9.0)
            Visual C++ 2010   (ATL 10.0)
            Visual C++ 2012   (ATL 11.0)
            Visual C++ 2013   (ATL 12.0)
            Visual C++ 2015   (ATL 14.0)
 
    SDK (optional):
            Any Platform SDK from January 2000 release up to the latest Windows SDK
 
    Windows CE development:
            eMbedded Visual C++ 3.0 - Pocket PC, Pocket PC 2002
            eMbedded Visual C++ 4.0 - STANDARDSDK_410, Pocket PC 2003, Smartphone 2003,
                                                     STANDARDSDK_500, Pocket PC 2003 SE, Smartphone 2003 SE
            Visual C++ 2005 - Pocket PC 2003 SE, Smartphone 2003 SE, STANDARDSDK_500,
                                       Windows Mobile 5.0 (Pocket PC and Smartphone),
                                       Windows Mobile 6.0 (Standard and Professional)
            Visual C++ 2008 - Pocket PC 2003 SE, Smartphone 2003 SE, STANDARDSDK_500,
                                       Windows Mobile 5.0 (Pocket PC and Smartphone),
                                       Windows Mobile 6.0 (Standard and Professional)
 
 
Packing List
 
File Name:	Description:
readme.html	this file
MS-PL.txt	Microsoft Public License
 
include\
    atlapp.h	message loop, interfaces, general app stuff
    atlcrack.h	message cracker macros
    atlctrls.h	standard and common control classes
    atlctrlw.h	command bar class
    atlctrlx.h	bitmap button, check list view, and other controls
    atlddx.h	data exchange for dialogs and windows
    atldlgs.h	common dialog classes, property sheet and page classes
    atldwm.h	DWM support classes
    atlfind.h	Find/Replace support for Edit and RichEdit
    atlframe.h	frame window classes, MDI, update UI classes
    atlgdi.h	DC classes, GDI object classes
    atlmisc.h	WTL ports of CPoint, CRect, CSize, CString, etc.
    atlprint.h	printing and print preview
    atlres.h	standard resource IDs
    atlresce.h	standard resource IDs for Windows CE
    atlribbon.h	RibbonUI support
    atlscrl.h	scrollable windows
    atlsplit.h	splitter windows
    atltheme.h	Windows XP theme classes
    atluser.h	menu class, USER object classes
    atlwince.h	specific support for Windows CE Mobile platforms
    atlwinx.h	extensions of ATL windowing support
 
Samples\
    Aero\...	Vista Aero glass showcase
    Alpha\...	Windows XP 32-bit (alpha) toolbar images
    BmpView\...	bitmap file view sample
    GuidGen\...	WTL version of the GuidGen sample
    ImageView\...	Full-featured PPC frame-view application
    MDIDocVw\...	WTL version of the MDI sample
    MemDlg\...	In-memory dialog sample
    MiniPie\...	port of the SDK sample for Mobile devices
    MTPad\...	multithreaded notepad sample
    MTPad7\...	MTPad with RibbonUI
    SPControls\...	Barebone SmartPhone dialog application
    TabBrowser\...	Web browser using TabView
    Wizard97Test\...	Wizard97 showcase sample
    WTLExplorer\...	Explorer-like application sample
 
AppWiz\
    setup.js	AppWizard setup program for all versions of Visual Studio
    Files\...	WTL AppWizard files
 
AppWizCE\
    setup80.js	AppWizard setup program for VC++ 2005
    setup90.js	AppWizard setup program for VC++ 2008
    Files\...	WTL AppWizard CE files
 
AppWizMobile\
    setup80.js	AppWizard Mobile setup program for VC++ 2005
    setup90.js	AppWizard Mobile setup program for VC++ 2008
    Files\...	WTL AppWizard Mobile files
 
 
Class Overview
 
usage:       	mi base	   -	   a base class (multiple inheritance)
 	client	   -	   wrapper class for a handle
 	as-is	   -	   to be used directly
 	impl	   -	   implements a window (has WindowProc) or other support
 	helper	   -	   a helper class
 	base	   -	   implementation base class
 
class name:	usage:	description:

App/module support
CAppModule	as-is	app support, CComModule derived
CServerAppModule	as-is	module for COM servers
CMessageLoop	as-is	message loop
CMessageFilter	mi base	message filter interface
CIdleHandler	mi base	idle time handler interface

Frame windows
CFrameWindowImplBase	base	 
CFrameWindowImpl	impl	frame window support
COwnerDraw	impl mi base	owner-draw msg map and handlers
CDialogResize	impl mi base	support for resizing dialogs
CDoubleBufferImpl	impl mi	double-buffer painting support
CDoubleBufferWindowImpl	impl	double-buffer painting window

MDI windows
CMDIWindow	client	MDI methods
CMDIFrameWindowImpl	impl	MDI frame window
CMDIChildWindowImpl	impl	MDI child window

Update UI
CUpdateUIBase	base	 
CUpdateUI	mi base class	provides support for UI update
CDynamicUpdateUI	mi base class	provides dynamic support for UI update

Standard controls
CStatic	client	static ctrl
CButton	client	button ctrl
CListBox	client	list box ctrl
CComboBox	client	combo box ctrl
CEdit	client	edit ctrl
CEditCommands	mi	standard edit command support
CScrollBar	client	scroll bar ctrl

Common controls
CImageList	client	image list
CListViewCtrl	client	list view ctrl
CTreeViewCtrl	client	tree view ctrl
CTreeItem	helper	 
CTreeViewCtrlEx	client	uses CTreeItem
CHeaderCtrl	client	header bar ctrl
CToolBarCtrl	client	toolbar ctrl
CStatusBarCtrl	client	status bar ctrl
CTabCtrl	client	tab ctrl
CToolTipCtrl	client	tool tip ctrl
CToolInfo	helper	 
CTrackBarCtrl	client	trackbar ctrl
CUpDownCtrl	client	up-down ctrl
CProgressBarCtrl	client	progress bar ctrl
CHotKeyCtrl	client	hot key ctrl
CAnimateCtrl	client	animation ctrl
CRichEditCtrl	client	rich edit ctrl
CRichEditCommands	mi	std rich edit commands support
CDragListBox	client	drag list box
CDragListNotifyImpl	impl mi class	support for notifications
CReBarCtrl	client	rebar ctrl
CComboBoxEx	client	extended combo box
CDateTimePickerCtrl	client	date-time ctrl
CFlatScrollBarImpl	mi impl	flat scroll bars support
CFlatScrollBar	as-is	flat scroll bars support
CIPAddressCtrl	client	IP address ctrl
CMonthCalendarCtrl	client	month calendar ctrl
CCustomDraw	impl mi class	custom draw handling support

Windows CE controls
CCECommandBarCtrl	client	command bar ctrl
CCECommandBandsCtrl	client	command bands ctrl

Property sheet & page
CPropertySheetWindow	client	 
CPropertySheetImpl	impl	property sheet
CPropertySheet	as-is	 
CPropertyPageWindow	client	 
CPropertyPageImpl	impl	property page
CPropertyPage	as-is	 
CAxPropertyPageImpl	impl	property page with ActiveX
CAxPropertyPage	as-is	 
CWizard97SheetWindow	client	 
CWizard97SheetImpl	impl	Wizard97 property sheet
CWizard97Sheet	as-is	 
CWizard97PageWindow	client	 
CWizard97PageImpl	impl	Wizard97 property page
CWizard97ExteriorPageImpl	impl	Wizard97 exterior page
CWizard97InteriorPageImpl	impl	Wizard97 interior page
CAeroWizardFrameWindow	client	 
CAeroWizardFrameImpl	impl	Aero Wizard frame
CAeroWizardFrame	as-is	 
CAeroWizardPageWindow	client	 
CAeroWizardPageImpl	impl	Aero Wizard page
CAeroWizardPage	as-is	 
CAeroWizardAxPageImpl	impl	Aero Wizard page with ActiveX
CAeroWizardAxPage	as-is	 

Common dialogs
CFileDialogImpl	impl	GetOpenFileName/GetSaveFileName
CFileDialog	as-is	 
CMultiFileDialogImpl	impl	Multi-select GetOpenFileName
CMultiFileDialog	as-is	 
CShellFileDialogImpl	base	 
CShellFileOpenDialogImpl	impl	Shell File Open dialog
CShellFileOpenDialog	as-is	 
CShellFileSaveDialogImpl	impl	Shell File Save dialog
CShellFileSaveDialog	as-is	 
CFolderDialogImpl	impl	directory picker
CFolderDialog	as-is	 
CFontDialogImpl	impl	ChooseFont common dialog
CFontDialog	as-is	 
CRichEditFontDialogImpl	impl	ChooseFont for rich edit
CRichEditFontDialog	as-is	 
CColorDialogImpl	impl	ChooseColor common dialog
CColorDialog	as-is	 
CPrintDialogImpl	impl	PrintDlg common dialog
CPrintDialog	as-is	 
CPrintDialogExImpl	impl	new Win2000 print dialog
CPrintDialogEx	as-is	 
CPageSetupDialogImpl	impl	PageSetupDlg common dialog
CPageSetupDialog	as-is	 
CFindReplaceDialogImpl	impl	FindText/ReplaceText
CFindReplaceDialog	as-is	 

User support
CMenu	client	menu support
CMenuItemInfo	as-is	MENUITEMINFO wrapper
CAccelerator	client	accelerator table
CIcon	client	icon object
CCursor	client	cursor object
CResource	client	generic resource object

GDI support
CDC	client	DC support
CPaintDC	client	for handling WM_PAINT
CClientDC	client	for GetDC
CWindowDC	client	for GetWindowDC
CMemoryDC	client	in-memory DC
CPen	client	GDI pen object
CBrush	client	GDI brush object
CLogFont	as-is	LOGFONT wrapper
CFont	client	GDI font object
CBitmap	client	GDI bitmap object
CPalette	client	GDI palette object
CRgn	client	GDI region object

Enhanced controls
CCommandBarCtrlImpl	impl	command bar
CCommandBarCtrl	as-is	 
CBitmapButtonImpl	impl	bitmap button
CBitmapButton	as-is	 
CCheckListViewCtrlImpl	impl	check list box
CCheckListViewCtrl	as-is	 
CHyperLinkImpl	impl	hyper link control
CHyperLink	as-is	 
CWaitCursor	as-is	wait cursor
CCustomWaitCursor	as-is	custom and animated wait cursor
CMultiPaneStatusBarCtrlImpl	impl	status bar with multiple panes
CMultiPaneStatusBarCtrl	as-is	 
CPaneContainerImpl	impl	pane window container
CPaneContainer	as-is	 
CSortListViewImpl	impl	sorting list view control
CSortListViewCtrlImpl	impl	 
CSortListViewCtrl	as-is	 
CTabViewImpl;	impl	tab view window
CTabView	as-is	 

Scrolling window support
CScrollImpl	impl mi	scrolling support
CScrollWindowImpl	impl	scrollable window
CMapScrollImpl	impl mi	scrolling support with map modes
CMapScrollWindowImpl	impl	scrollable window with map modes
CZoomScrollImpl	impl mi	zooming support
CZoomScrollWindowImpl	impl	zooming window
CScrollContainerImpl	impl	scroll container window
CScrollContainer	as-is	 

Splitter window support
CSplitterImpl	impl mi	splitter support
CSplitterWindowImpl	impl	splitter window
CSplitterWindow	as-is	 

Theming support
CTheme	client	Windows XP theme
CThemeImpl	impl	theming support for a window

Buffered paint and animation support
CBufferedPaint	as-is	buffered paint
CBufferedPaintImpl	impl mi	buffered paint support
CBufferedPaintWindowImpl	impl	window with buffered paint
CBufferedAnimation	as-is	buffered animation
CBufferedAnimationImpl	impl mi	buffered animation support
CBufferedAnimationWindowImpl	impl	window with buffered animation

Edit and RichEdit Find/Replace support
CEditFindReplaceImplBase	base	 
CEditFindReplaceImpl	mi	Edit Find/Replace support
CRichEditFindReplaceImpl	mi	RichEdit Find/Replace support

Printing support
CPrinterInfo	as-is	print info support
CPrinter	client	printer handle wrapper
CDevMode	client	DEVMODE wrapper
CPrinterDC	client	printing DC support
CPrintJobInfo	client	print job info
CPrintJob	client	print job support
CPrintPreview	mi	print preview support
CPrintPreviewWindowImpl	impl	print preview window
CPrintPreviewWindow	as-is	 
CZoomPrintPreviewWindowImpl	impl	zooming print preview window
CZoomPrintPreviewWindow	as-is	 

Miscellaneous
CSize	as-is	WTL port of MFC's CSize
CPoint	as-is	WTL port of MFC's CPoint
CRect	as-is	WTL port of MFC's CRect
CString	as-is	WTL port of MFC's CString
CWinDataExchange	mi	data exchange for controls
CRecentDocumentList	mi or as-is	support for MRU list
CFindFile	as-is	file search support

In-memory dialog
CDialogBaseUnits	helper	dialog units helper
CMemDlgTemplate	as-is	In-memory dialog template
CIndirectDialogImpl	impl	In-memory dialog class

Task dialog
CTaskDialogImpl	impl	Task Dialog in Vista
CTaskDialog	as-is	 

DWM classes
CDwm	client	DWM handle warapper
CDwmImpl	impl base	DWM support
CDwmWindow	impl	DWM window support
CDwmThumbnail	client	DWM thumbnail wrapper
CAeroControlImpl	impl	support for Aero controls

Ribbon classes
CRibbonUpdateUI	mi base	automatic mapping of ribbon UI elements
RibbonUI::CtrlImpl	base impl	base class for all ribbon controls
RibbonUI::CommandCtrlImpl	base impl	base class for ribbon controls
RibbonUI::CollectionImplBase	base	base class for all RibbonUI collections
RibbonUI::CollectionImpl	impl	RibbonUI collections
RibbonUI::CollectionCtrlImpl	impl	specializable class for ribbon collection controls
RibbonUI::ToolbarGalleryCtrlImpl	base impl	base class for ribbon toolbar gallery controls
RibbonUI::CRibbonImpl	impl	Ribbon implementation class
CRibbonFrameWindowImplBase	base	base frame class for Ribbon
CRibbonFrameWindowImpl	impl	Ribbon frame window class
CRibbonMDIFrameWindowImpl	impl	Ribbon MDI frame window class
CRibbonPersist	as-is	Ribbon persistance support

Windows CE support
CStdDialogBase	base	standard dialog base class
CStdDialogImpl	impl	standard dialog implementation
CStdSimpleDialog	as-is	standard simple dialog
CStdDialogResizeBase	base	orientation aware standard dialog base class
CStdDialogResizeImpl	impl	orientation aware standard dialog implementation
CStdSimpleDialogResizeImpl	impl	standard resizing simple dialog implementation
CStdOrientedDialogBase	base	oriented dialog base class
CStdOrientedDialogImpl	impl	oriented dialog implementation
CStdSimpleOrientedDialog	as-is	standard simple oriented dialog
CAppInfoBase	base	application state save/restore to registry
CAppInfoT	impl	CAppInfoBase constructed from a CAppWindow<T>
CAppWindow<>	mi	PPC/SmartPhone well-behaved application window class
CAppDialog	mi	PPC/SmartPhone well-behaved application non-modal dialog class
CAppStdDialogImpl	impl	PPC/SmartPhone implementation of non-modal standard dialog application
CFullScreenFrame	impl	Full screen frame class
CZoomScrollImpl	mi	WinCE zooming implementation
CHtmlCtrl	client	HTML control
CRichInkCtrl	client	RichInk control
CInkXCtrl	client	InkX control
CVoiceRecorderCtrl	client	VoiceRecorder control
CDocListCtrl	client	DocList control
CCapEdit	client	CapEdit control
CTTStatic	client	TT Static control
CTTButton	client	TT Button control
CSpinCtrl	client	Spin control
CSpinListBox	client	Spin List Box control
CExpandListBox	client	Expand List Box control
CExpandEdit	client	Expand Edit control
CExpandCapEdit	client	Expand CapEdit control
 
 
ATL/WTL AppWizard
 
ATL/WTL AppWizard generates starting code for a WTL application. It has options to create code for different application types and features.
 
You can choose the following options:
Application type (SDI, multi thread SDI, MDI, TabView, Explorer, dialog based)
Support for hosting ActiveX controls
COM server support
Class implementation in .CPP files
Common Control manifest
Unicode character set
Toolbar, rebar, command bar, status bar
View window, and it's type (generic, dialog based form, or a list box, edit, list view, tree view, rich edit based, HTML page, scroll window)
For dialog based apps or a form based view window - support for hosting ActiveX controls in the dialog
 
ATL/WTL AppWizard supports VC++ .NET 2002 and 2003, VC++ 2005, 2008, 2010, 2012, 2013, and 2015.
 
 
Support for Windows CE
 
WTL fully supports building projects for the Windows CE platforms. The initial support for Windows CE was implemented primarily for eMbedded Visual C++ 4.0 with Pocket PC 2003 and SmartPhone 2003 SDKs. However, it can be used with other versions and configurations. For instance, Standard SDK 4.1 or 5.0 is supported as well. Considerable effort was made to provide the best Windows CE support, however, there might be some limitations because different platforms provide different programming support. SmartDevice projects with Visual Studio 2005 and 2008 are also supported, and it also includes an AppWizard for VS2005 and VS2008.
 
The support for Windows CE was not designed to port projects for the desktop version of Windows as-is to the Windows CE platforms, but to allow use of the same library, WTL, for both desktop Windows and Windows CE. Applications for Windows CE are often designed in a different way, and they use different platform services. WTL depends on the version of ATL provided with each Windows CE platform, and supports controls and services that are appropriate and supported for each Windows CE platform.
 
 
Support for Visual C++ Express
 
Note: Visual Studio Express is not the only or the best free development environment any more - Visual Studio Community provides a complete release of Visual Studio for free.
 
WTL supports using Visual C++ Express Edition to build projects. Since Visual C++ Express ships without ATL, you have to use a version of ATL that ships with Windows Driver Kit 7.1.0 or Platform SDK (Windows Server 2003 R2 Platform SDK).
 
Windows Driver Kit 7.1.0 contains ATL version 8, while Platform SDK has ATL version 3. We recomend ATL from Windows Driver Kit since it is newer and better version. However, you can still use ATL from Platform SDK since WTL still fully supports ATL3.
 
The WTL App Wizard can be installed by running AppWiz\setup.js program. The App Wizard generates code in the stdafx.h file that allows use of ATL. That code is used if _WTL_SUPPORT_EXTERNAL_ATL is defined, so you can comment the line in stdafx.h that defines _WTL_SUPPORT_EXTERNAL_ATL to use the project with different versions of Visual C++ or ATL.
 
Note that Release builds might generate some warnings, since ATL3 from Platform SDK is an old version of ATL which doesn't quite match the newer compiler and CRT files. You can ignore those warnings, as they do not indicate any real problems with the code.
 
Supported VC++ versions:
VC++ 2005 Express
VC++ 2008 Express
VC++ 2010 Express
VC++ Express 2012 for Windows Desktop
VC++ Express 2013 for Windows Desktop
VC++ Express 2015 for Windows Desktop
 
Supported ATL versions:
from Platform SDK (ATL 3)
from Windows Driver Kit (ATL 8)
 
Download Links:
           Visual Studio Community 2013 and 2015
           Visual Studio Express 2013 and 2015 for Windows Desktop
           Visual Studio Express 2012 for Windows Desktop
 
           Windows Driver Kit Version 7.1.0
 
Older versions are not avilable for download any more. If you already have them, you can use them as descibed here.
 
 
Notes
 
~    WTL provides several classes that are also present in ATL 7.0 and 7.1. The classes are: CSize, CPoint, CRect, and CString in atlmisc.h. While their existence will not cause any problems, their usage might. You should qualify the class you want to use with a namespace to resolve ambiguity, either ATL or WTL namespace, depending on which implementation you want to use. Alternatively, you can conditionally exclude WTL implementations, by defining preprocessor symbol _WTL_NO_WTYPES for CSize, CPoint, and CRect; and _WTL_NO_CSTRING for CString.
 
~    If you use WTL 9.0 with VC++ 6.0/ATL 3.0 and define _ATL_STATIC_REGISTRY, you'll get errors referring to the ambiguous symbol ATL. This is caused by a bug in ATL 3.0 - in atlbase.h, the file statreg.h is included inside of the ATL namespace, and it contains another namespace ATL declaration. Because of that, the compiler cannot decide between ATL:: and ATL::ATL:: namespaces. The solution is either to fix the atlbase.h, or to surround atlbase.h include declaration with following statements:
 
    #define ATL   ATLFIX
    #include <atlapp.h>
    #undef ATL
    namespace ATL = ::ATLFIX;
 
~    Windows XP allows applications to use Common Controls version 6, which supports only Unicode applications. While WTL allows creation of Ansi applications that use Common Controls 6, that should be used only for test programs and is not recommended or supported for released projects. If you want to use Common Controls 6, build your application as Unicode.
 
~    If you build your app that hosts ActiveX controls with VC++ 7.x, you can see this assert failing:

    !InlineIsEqualGUID(*m_plibid, GUID_NULL) && "Did you forget to pass the LIBID to CComModule::Init?"

There are two ways to fix this:
In the main .CPP file of your project, replace the line
    hRes = _Module.Init(NULL, hInstance);
with this one
    hRes = _Module.Init(NULL, hInstance, &LIBID_ATLLib);
 
Compile you project with _ATL_DLL defined (dynamic link to ATL)
~    Several of the sample programs included with WTL were extended to support building for Windows CE. These samples are not specially redesigned for Windows CE, but just modified to allow you to compile and run them on the Windows CE platforms. The samples are: BmpView, GuidGen, and MTPad.
 
~    WTL supports building projects with EVC++ 3.0 only for Pocket PC and Pocket PC 2002 platforms, as other platforms don't provide minimum support for ATL or other required libraries.
 
~    The old AppWizards for VC++ 6.0 and eVC++ 4.0/3.0 are not included in this version of WTL because they cannot be a part of an Open Source project. They are still available in the previous release, WTL 7.1.
 
~    Visual Studio 2012 and higher use default subsystem version 6.0 (Windows Vista). Previous versions of Visual Studio used 5.01 (Windows XP). That means that applications built with Visual Studio 2012 and higher cannot run on Windows XP. Attempting to run would result in an error that it is not a valid Win32 application. If you want to run your applications on Windows XP, you need to change subsystem version to 5.01. You can do that by going to Project Properties -> Linker -> System -> Minimum Required Version, and entering 5.01 as a value.
 
 
Changes Between WTL 9.1 and 9.0
 
New and improved:
Full compatibility with VS2015
NuGet support and package
Microsoft Public License (MS-PL)
New sample: MemDlg - demonstrates use of in-memory dialogs
 
Fixes and enhancements:
Fixes for code analysis warnings
Fixes for strict const-qualification conformance (/Zc:strictStrings)
CEditFindReplaceImpl::UseShadowBuffer(): Use AtlGetCommCtrlVersion() instead of GetProcAddress()
Misc improvements: missing initialization, undefined messages, better #ifdefs
CFrameWndClassInfo: Use GetSystemMetrics() for icon sizes
BEGIN_MSG_MAP_EX and BEGIN_DDX_MAP: Fix for C4555: expression has no effect
CResource::LoadEx(): Fix for the wrong order for parameters to ::FindResourceEx()
CPaneContainerImpl:
New extended styles: PANECNT_DIVIDER and PANECNT_GRADIENT
Fixed background drawing for close button
CImageListManaged: Fix for assert when using attach or operator =
WTLExplorer sample cleanup
GenericWndClass::Register(): Fix for Windows CE
App Wizard: Improved code for generating project configurations
CSplitterImpl::OnCaptureChanged(): Fixed so it moves splitter bar only if move was in progress
CDynamicUpdateUI::UIRemoveUpdateElement() leaks memory if UPDUI_TEXT is set
CToolInfo and CToolTipCtrl: nIDTool argument should be UINT_PTR instead of UINT
CSplitterImpl: Added GetSplitterPosPct()
CCommandBarCtrlImpl: Fixed incorrect use of m_wndParent when AttachToWindow() is used
 
 
Changes Between WTL 9.0 and 8.0
 
New and improved:
Full compatibility with VS2008, VS2010, VS2012, and VS2013
New CRegKeyEx class for uniform support for registry
New MinCrtHelper functions for uniform support for _ATL_MIN_CRT
New DWM classes in atldwm.h
New Ribbon classes in atlribbon.h
New CDialogBaseUnits class
Extended DDX support to TabCtrl, ComboBox, ListBox and ListView selection index
Improved font handling in CHyperLink, CPaneContainer, CTabView
CHyperlink: Added options for auto-create link font and single-line mode
CBitmapButtonImpl: Added checked state, GetCheck()/SetCheck(), and check mode extended styles
UpdateUI: Added support for radio menu items for popup menus
Added support for new VersionHelpers.h in WinSDK 8.1 - GetVersionEx() is now deprecated
Improved global support for old SDK headers, and for original headers in VC6 and VC7.x
Global support for builds with NOMINMAX defined
Global support for builds with STRICT_TYPED_ITEMIDS defined
Global support for builds with _ATL_ALL_USER_WARNINGS defined
Splitter Window:
Added keyboard handling
Added default position for splitter bar
Changed orientation from template argument to data member to reduce memory use
Added SPLIT_GRADIENTBAR and SPLIT_FIXEDBARSIZE extended styles
Added CImageListManaged to manage the lifetime of wrapped image list
Added Vista standard menu bar look option for Command bar
Added new Rich Edit wrappers for _RICHEDIT_VER >= 0x0800
Added new Win8 methods to Theme classes
Added override of SubclassWindow() to CSplitterWindowImpl, CPaneContainerImpl, CTabViewImpl,
  CScrollImpl, CMapScrollImpl, CZoomScrollImpl, and CScrollContainerImpl
CZoomScrollImpl:
Added zoom child windows option
Added zoom scale max limit
AppWizard:
Support for VS2008, VS2010, VS2012, and VS2013
New universal setup for all versions of Visual Studio
Support for ribbon control
Updated samples and added VS2005 project files
New sample: MTPad7 - demonstrates Ribbon UI
 
Fixes and enhancements:
General:
Fixed security warning for _vstprintf in atlapp.h
Added RunTimeHelper::IsThemeAvailable that detects if themes can be used in the app
VS2012: DLL version functions are defined as they are removed from ATL11
Added CWndProcThunk initialization for _ATL_VER >= 0x0800
Added RunTimeHelper::SizeOf_TOOLINFO() for different Windows versions at runtime
Added AtlCreateControlFont()
 
Controls:
Extended CListViewCtrl::SelectItem() to multi-selection list view controls
Added another variant of CListViewCtrl::FindItem for strings
Added new CToolBarCtrl methods - InsertSeparator() and AddSeparator()
Added CToolBarCtrl::GetItemDropDownRect()
Added another variant of CToolTipCtrl::TrackActivate()
 
Cracked Handlers:
Fixed handlers with menu arguments
Fixed MSG_WM_SYSCOMMAND handler
Added MSG_WM_MOUSEHWHEEL handler
 
App Wizard:
Fix for TabView project code generation
Improved generated code for VC++ Express to support various versions of ATL
Fix for missing UIUpdateChildWindows() in dialog projects
 
App Wizard CE / App Wizard Mobile:
Updated AppWizCE for VS2008 - used different CLSID for Platforms object
Fix: VS2008 uses _SECURE_ATL code only
Fix for resource creation failure
 
Misc:
Fix: CLogFont uses ::GetDeviceCaps with wrong default hDC = NULL
Fixed CPen::GetExtLogPen
Fixed CFrameWindowImpl::OnToolTipText*() handlers not to reset text buffer
Added support for chevron menus for multi-line toolbars
Fix: CFileDialog(false) fails on Windows Mobile 5 or 6
Fix: CFolderDialog::SetOKText should use lParam for string
Added CFolderDialog::SetPidlRoot()
Fixed CMemDlgTemplate::AddControl
Added option to disable item dragging in CTabViewImpl
Fixed CTabView::ShowTabControl(false) and UpdateLayout() to hide empty space
CTabView: Fixed value of the active page when inserting pages before it
PaneContainer: Added support for vertical title bar text
atlsplit.h: Added missing support for WM_PRINTCLIENT
Fix: CScrollImpl should not scroll horizontally if not needed
Fixed CScrollImpl::ScrollToView() to use offset correctly
Fixed CPrintDialogExImpl::GetDefaults()
atltheme.h: Added CBufferedAnimation::StopAllAnimations()
Added support for I64 format to CString::Format()
Fix: CStdIndirectDialogImpl - DLGTEMPLATEEX not supported on Mobile devices
Fix: Missing CRichInkCtrlT::SetSel(), added CRichInkCtrlT::Undo()
 
 
Changes Between WTL 8.0 and 7.5
 
New and improved:
RunTimeHelper functions for correct struct sizes on different versions of Windows
ModuleHelper functions for uniform support of ATL3 and ATL7 module classes
SecureHelper functions for support of secure and non-secure run-time functions
Support for new Vista features:
Support for new messages for common controls, dialogs, etc.
Support for TaskDialog
New Shell file dialogs (IFileOpenDialog and IFileSaveDialog)
New Aero Wizard support classes
New classes for Buffered Paint and Buffered Animation
New TabView classes
New dialog class that uses in-memory dialog templates
New CMultiFileDialogImpl and CMultiFileDialog classes that support multi-select file dialogs
Added message cracker handler prototypes for all handlers
Replaced use of _alloca with CTempBuffer everywhere (and added CTempBuffer version for ATL3)
New classes for find/replace support for Edit or RichEdit
New class CFileDialogEx that supports GetOpenFileNameEx for Windows Mobile 5
New features for the App Wizard:
New default version values
Unicode build option
Support for TabView applications
Support for Explorer applications
Updates for the desktop App Wizard:
Added calls to set font for views based on controls that use font
Added scroll window as another view type
Support for VC2005 Express:
Setup for VS2005x
Changes in default.js to take into account that VC2005x does not have a resource editor
Generated code allows use of ATL3 from the Platform SDK
New AppWizard for Mobile 2003 and 2005 platforms
New samples:
Aero - demonstrates the Vista Glass UI
MiniPie - Windows Mobile 2005 PPC and Smartphone sample
TabBrowser - a web browser using TabView class
MTPad sample updated to show usage of CRichEditFindReplaceImpl and CEditCommands/CRichEditCommands
 
Fixes and enhancements:
Command Bar:
Added support for menu items with bitmaps on Vista
Fix: Keyboard cues shown even if the window is disabled
 
CFolderDialog:
Added support for PIDLs in addition to the file path
Replaced use of SHGetMalloc with CoTaskMemFree
 
Scroll Windows:
Fix: CZoomScrollImpl - some methods should be overridable
Added support for WM_MOUSEHWHEEL in CScrollImpl
 
App Wizard:
Fix: AppWizard fails to add files if C:\Temp does not exist
Fix: App Wizard generates security warning when loaded
Fix: App Wizard generates level 4 warning for modal dlg project
Fix: App Wizard setupXX.js scripts silently fail on Vista
Fix: Added code to unregister message filer and idle processing
Fix: Added WS_CLIPSIBLINGS to dialog forms to avoid rebar drawing problems
 
App Wizard CE:
Fix: App Wizard CE should not have rich edit as a view option
Fix: App Wizard CE generates level 4 warnings for single instance apps
Added support for Windows Mobile 6 SDKs
 
Cracked Handlers:
Fix: Corrected MSG_WM_TIMER and handler prototype, removed unused argument (breaking change)
Fix: atlcrack.h does not support WTL namespace
 
CDialogResize:
Added SetIcon(NULL, FALSE) for CDialogResize to remove the generic icon for resizable dialogs
Fix: Enabled size/move for both X and Y
Added center flags for controls
 
CFrameWindowImpl:
Fix: Const issue with title argument of AddSimpleReBarBand
Fix: DECLARE_FRAME_WND_CLASS definition missing WTL namespace
 
Windows CE:
Fix: Some symbols not defined for CE 4.0
Fix: Incorrect WinCE exclusions
Fix: Pocket PC - assert after navigating a CHyperLink
Fix: Property sheet with listview on WM5.0 causes stack overflow
Fix: CFindFile::GetFilePath() fails on diskless root requests
Fix: VS 2005 dialog editor bug - DS_FIXEDSYS used but not defined
Fix: Windows Mobile 2005 compatibility issues
Fix: CFullScreenFrame on Smartphone 20003
Fix: SmartPhone back key handling in CAppWindow
Added orientation aware support to CAppStdDialogImpl
Added CAxDialogImpl base for CStdDialogImpl, CStdDialogResizeImpl and CStdOrientedDialogImpl
Added various CStdDialogxxx enhancements
Fix: CStdDialogBase does not scale dialog title on VGA
Fix: DIBINFO16 triggers code analysis warning
Added LPCTSTR AtlLoadString(UINT uID) - CE only overload
Added imaging draw support to CZoomScrollImpl
Added CBottomTabViewImpl and CBottomTabView classes for PPC
 
CFindFile:
Fix: CFindFile class uses CRT functions
Fix: FindFile() uses lstrcpy without checking length
 
General:
Fix: Adding ReBar bands fails with new Windows SDK
Added support for relative include paths
Fix: Using std::min and std::max
Fix: Problems using WTL with MFC
Improved support for Secure CRT
Changed implementation of CSize, CPoint, CRect, and CString to be inside class definitions
atltheme.h: Corrected method signatures for differences in uxtheme.h versions
Replaced malloc/free with new/delete where appropriate
 
Misc:
Fix: CString::FormatV can cause GPF with Unicode strings
CHyperLink: Added handler for WM_SIZE
Fix: CTheme needs constructor from HTHEME handle
Added Add* methods to several control classes in atlctrls.h to augment Insert* methods
Fix: Incorrect casting in CRichEditCtrl::GetLine()
Fix: CTreeViewCtrl::GetItemState changed to return only state-bits as specified by mask
Fix: CBitmapButton::DoPaint - wrong button image
Added another variant of CDCT::Drawtext with LPTSTR argument that allows text change
Fix: CRecentDocumentListBase::AddToList() uses lstrcpy
Fix: AtlLoadString(uID, lpBuffer, nBufferMax) has unnecessary code
Fix: CCursor::LoadOEMCursor asserts on IDC_HAND
Fix: Memory leak when using CRT functions while printing
Fix: Undefined CString namespace
CPaneContainer: Added border styles
CSplitterImpl: Added SetSplitterPosPct, and changed App Wizard code to use it
 
 
Changes Between WTL 7.5 and 7.1
 
New and improved:
VS2005 Compatibility: Added support for Visual Studio 2005 - both desktop and Windows CE
Classes for icons, cursors, accelerator tables
CSortListViewImpl, CSortListViewCtrlImpl, and CSortListViewCtrl classes
Impl classes for Wizard 97 style wizards: CWizard97Sheet, CWizard97Page, CWizard97ExteriorPage, CWizard97InteriorPage
CMemoryDC and CDoubleBufferWindowImpl classes
Windows CE specific classes in new header, atlwince.h
CScrollContainer class
CZoomScrollImpl and CZoomScrollWindowImpl classes
CZoomPrintPreviewWindowImpl and CZoomPrintPreviewWindow classes
Global functions: AtlGetBitmapResourceInfo, AtlGetBitmapResourceBitsPerPixel
New REFLECT_* macros to enable selective reflection of messages
App Wizard: Added App Wizard for VS2005
App Wizard: Added App Wizard for Windows CE for VS2005
New samples: WTLExplorer, ImageView, SPControls
 
Fixes and enhancements:
Command Bar:
DrawBitmapDisabled() doesn't work correctly on Longhorn
Submenu size not correct if command bar is off-screen
Added handler for WM_SETTINGCHANGE to improve theme color changes
Better support for 8/16/24-bit images
Command Bar with 2 Levels of submenus remains active
Hook procedure fails to call next hook
OnDestroy() should not decrement hook use if AttachToWindow() is used
 
MDI Command Bar:
Grows bigger if you switch between two maximized MDI child window types
Move all hook messages processing to a separate function and use pT
MDI icon & buttons should have themed background
Should make MDI buttons gray when inactive
 
CString:
Helper functions not overloaded properly
Some return types are 'const CString&' and could be just 'CString&'
FormatV() passes size in characters to _alloca, should be in bytes
Fixed stack corruption in FormatV()
Improved boundaries checking for integer overflows/underflows
 
CScrollImpl:
Scroll bars problem when changing range
SetScrollOffset() doesn't move child windows
Range and thumb drawing problems
Possible overflow in OnMouseWheel()
Support for SIF_DISABLENOSCROLL
Added ScrollToView methods
 
CMapScrollImpl:
SetScrollSize() incorrectly inverts xMin and xMax
SetScrollSize() uses bRedraw = NULL
 
CTheme:
GetThemeFont() bad parameter ordering
Uses LOGFONT and TEXTMETRIC incorrectly (SDK header problem)
 
CFrameWindowImpl:
Improved sizing for Windows CE
CreateSimpleToolBarCtrl() should handle 24-bit bitmaps
Changed WinCE CCECommandBarCtrl typedef and added a PPC CMenuBarCtrl
UpdatesBarPosition() doesn't take Windows CE command bar into account
 
CDialogResize:
Enabled use for Windows CE
Add WS_EX_DLGMODALFRAME to prevent empty icon
 
CReBarCtrl:
Background not painted when resized
Fixed typo in LockBands()
MaximizeBand needs BOOL fIdeal argument
 
CRichEdit:
GetSelText() should support UNICODE strings
GetSelText() uses lpstr instead of lpstrText
 
CHyperLink:
Added _xttoi() helper to avoid CRT in _ATL_MIN_CRT
Fixed resource leak by destroying tooltip window
 
CPropertySheetImpl:
Improved support for Windows CE
Sheet without title generates a memory fault on Windows CE
 
CFolderDialog:
Add a way to set an initial folder
Uses BFFM_IUNKNOWN which is not always defined
 
Update UI:
Add support to dynamically add UpdateUI elements
UIUpdateMenuBarElement() should use EnableMenu() instead of SetMenuItemInfo() for Windows CE
 
CDC:
FillSolidRect() should restore background color
GetClipRgn() method missing
 
Printing:
CPrinter::CreatePrinterDC() and CreatePrinterIC() members should be const
CDevMode::CopyToHDEVMODE() is missing a call to GlobalUnlock()
 
AppWizard:
Use WTL subfolder to create WTL category for VC7.x and VC8
Rename files from WTLApp7x to WTLAppWiz, and add VS2005 setup file
Fixed setup for x64
 
General:
Redefinition of _MAX_FNAME with Dinkumware Standard C++ Library on Windows CE
Added ATLVERIFY macro for ATL3
Support warning level 4
Missing methods CToolBarCtrl::SetButtonInfo, InsertButton, CTabCtrl::SetItem, CComboBoxEx::InsertItem, SetItem
Missing support for WM_PRINTCLIENT
Removed usage of IsBad* functions
Fixed various compiler warnings
TCHAR bugs in various files
Improved Windows CE support and changes for Visual Studio 2005
 
Misc:
CMDIChildWindowImpl: HMENU should be destroyed in OnDestroy()
CStatic: Should use STM_SETIMAGE instead of STM_SETICON for SetIcon() on Windows CE
CButton: GetButtonStyle() uses wrong mask
CImageList: Made Duplicate() method const
CListViewCtrl: Made SubItemHitTest() method const
CTreeViewCtrl: GetItem() and SetItem() incorrectly restricted to _WIN32_IE >= 0x0500
CMonthCalendarCtrl: GetMonthRange() should be GetMaxTodayWidth()
CDateTimePickerCtrl: SetFormat() should have const argument
CBitmapButtonImpl: Fixed resource leak by destroying tooltip window
CMultiPaneStatusBarCtrlImpl: Cannot handle wide panes without resource strings
CCheckListViewCtrlImpl: Call CheckSelectedItems() through pT
CPaneContainerImpl: SetPaneContainerExtendedStyle() should use pT to call CalcSize()
CFindFile: Enabled for Windows CE
CPropertyPageImpl: Added handlers for callback messages
atlcrack.h: Added return value for MSG_WM_APPCOMMAND
CMenu: New method variants: AppendMenu, InsterMenu, ModifyMenu
CFont: Added arguments for bold and italic to CreatePointFont()
CSize: Added scalar operators for WTL::CSize and ATL::CSize
CRecentDocumentList: Allow changing the "DocumentCount" and "Document%i" registry values strings
CSplitterWindowImpl: Enabled use for Windows CE

 
Changes Between WTL 7.1 and 7.0
 
New and improved:
VC7 Compatibility: Support for ATL7 Module classes and critical sections and AppWizard setup for VC++ 7.1
Windows CE Support: Full compatibility with Windows CE platforms and AppWizard for eMbedded Visual C++
Namespace Support: Automatic "using ATL" (ATL7 only) or "using WTL" can now be turned off
CHyperLink New Features: not underlined, underlined when hover, command button, link tags
CCustomWaitCursor class supports custom and animated wait cursors
AtlCreateBoldFont() for creating bold version of an existing font
 
Fixes and enhancements:
CFrameWindowImpl:
CreateSimpleToolBarCtrl() - remove dead code, improve error checking, add a global function that uses it
Fix - PrepareChevronMenu() fails to get toolbar strings for Unicode
CFrameWindowImplBase::Create() - improve ASSERT not to use m_hWnd if creation fails
Fix - CFrameWndClassInfo::Register - should use %p formatting only for _WIN32_WINNT >= 0x0500 or for _WIN64
Fix - Chevron menus not positioned correctly with RTL
Fix - CMDIChildWindowImpl: Problems creating maximized child windows and handling focus
Fix - CMDIChildWindowImpl: Should activate on WM_MOUSEACTIVATE
 
UpdateUI:
Fix - Incorrectly clears default item from the system menu in MDI apps
Added UISetCheck with bool instead of int for the check state
 
DDX:
Fix - Doesn't provide a way to change floating point precision
Added DDX_CONTROL_HANDLE for non-CWindowImpl objects
Added DDX_Check variant with bool instead of int for the check state
 
Command Bar:
Fix - OnDrawItem() and OnMeasureItem() don't do a good check for owner-draw menu items
Fix - Disabled 32-bit images not painted correctly in 3D menu mode
Fix - Popup menus not positioned correctly with RTL
Fix - Uses GCL_HICONSM instead of GCLP_HICONSM with GetClassLongPtr()
 
MDI Command Bar:
Fix - Doesn't refresh icon if MDI children are different
OnAllHookMessages() - improve code to handle MDI child window class icon
Fix - OnNcLButtonDown() uses TPM_VERPOSANIMATION without checking Windows version
Fix - Maximized MDI buttons in wrong place for RTL
Should adjust cxIdeal for rebar bands for IE4
Add support for different top-level menu widths by handling ideal size for rebar bands
 
AppWizard:
Fix - Doesn't support MSDI application as a COM Server
Fix - MDI with Form View - stack overflow closing maximized MDI child windows
Fix - Generates VERSION resource name 'test1' regardless of the project name
Fix - Dialog project with control hosting doesn't derive a dialog from CAxDialogImpl
Fix - COM Server doesn't register type library
Fix - COM Server doesn't register AppID properly
 
CTreeViewCtrl:
Fix - GetItemData() needs better return value
Fix - GetItemState() should use TVM_GETITEMSTATE instead of TVM_GETITEM for IE5
GetItem() and SetItem() - added new variants that use TVITEMEX
Fix - SortChildren() should add recurse flag argument
Fix - CTreeItem doesn't support CTreeViewCtrlExT that has different TBase than CWindow
 
CThemeImpl:
Fix - Uses scalar delete instead of the vector one
Fix - EnableThemeDialogTexture() argument is BOOL instead of DWORD
 
CFolderDialog:
Fix - EnableOK() passes wrong arguments to BFFM_ENABLEOK
Fix - Always clears m_hWnd, which causes problem for nested messages
 
CDialogResize:
Fix - DlgResize_Init() forces dialog to be visible by using SetRedraw()
Forcing WS_THICKFRAME is not enough to make dialog resizable
Min track size should be used for child dialogs as well
Fix - DlgResize_PositionControl() incorrectly checks return value from MapWindowPoints()
 
CAppModule:
Fix - CAppModule methods not thread-safe
Fix - AddSettingChangeNotify() unusable in multithreaded apps because of delayed initialization
 
CString:
Fix - Delete() doesn't allow deleting more than the length of the string
Fix - Append() can cause buffer overrun
Fix - MakeReverse() can cause an infinite loop
Fix - _cstrstr() unnecessarily inefficient
Fix - FindOneOf() is not DBCS-aware
Fix - Format() does not recognize %E
Fix - TrimLeft() and TrimRight() are only half-way DBCS-aware
Fix - May cause assertions or undefined behavior with SBCS
 
CRecentDocumentList:
Fix - SetMaxEntries() has an incorrect ASSERT
Add CString variant of the GetFromList() method
Add a way to replace command IDs used for the MRU list
Add a way to replace registry key name
 
Misc:
CMessageLoop::Run() - improve the loop by checking bDoIdle before calling PeekMessage()
CServerAppModule: Clean-up unused code
Fix - CServerAppModule::MonitorProc() - no need to call _endthreadex()
Fix - CListBox::GetText() and CComboBox::GetLBText() (CString variants) don't check for LBERR/CB_ERR
Fix - CAxPropertyPageImpl doesn't create ActiveX controls with ATL7
Fix - CDC::GetTextExtentExPoint() missing
CDC::SetWindowExt() should have default value NULL for the lpSizeRet argument
Fix - CPropertySheetWindow missing methods for PSM_INSERTPAGE, PSM_SETHEADERTITLE, and PSM_SETHEADERSUBTITLE; AddPage should return BOOL
Fix - CMapScrollImpl::SetScrollSize() uses wrong variable
Fix - CHyperLink: WM_UPDATEUISTATE causes repaint without WM_PAINT
Fix - CUpDownCtrl::GetPos() returns incorrect value
Fix - CUpDownCtrl::GetPos32() doesn't have default arg value
Fix - CMultiPaneStatusBarCtrl: Always uses size grip for positioning panes
Fix - CTabCtrl::InsertItem() should return int, not BOOL
CReBarCtrl: Added LockBands() method
Fix - CFont: uninitialized variable passed to DPtoLP
Fix - CPrintDialogImpl: Crash when displaying Print Setup dialog
Fix - CPageSetupDialogImpl::PaintHookProc() - should use T* and return UINT_PTR instead of UINT
Fix - CPrintJob doesn't support printing to a file
Fix - CSplitterImpl: Doesn't handle WM_CAPTURECHANGED - can get in an invalid state
CRichEditCtrl: Add method for EM_SETTABSTOPS
Fix - CFindFile::GetFilePath() checks for a trailing slash, but doesn't use that info
 
General:
Fix - Problems compiling with /Zc:forScope ('for' loop scope conformance)
Use named constants instead of values for pixel sizes, buffer lengths, etc.
Support building with Managed C++ (/CLR)
CMenuItemInfo - add run-time support for different versions of Windows
CommCtrl.h change - additional fields in IMAGELISTDRAWPARAMS now depend on _WIN32_IE instead of _WIN32_WINNT
Fix - Incorrect usage of CRegKey::QueryStringValue()
Fix - Operator = for GDI and USER wrappers leaks handle if it's managed variant
Fix - GDI and USER wrappers break under self-assignments
Fix - Chaining messages with cracked handlers broken with ATL7
Initialize all variables and structures prior to use
Use new common control struct names
 
 
Changes Between WTL 7.0 and 3.1
 
New classes and features:
Support for new Common Controls v6 messages
Support for Visual Studio .NET and ATL 7.0
WTLApp70 - new AppWizard for Visual Studio .NET
CThemeImpl - implements support for Windows XP themes
CMDICommandBarCtrl - implements Command Bar for MDI applications
 
Fixes and enhancements:
Command Bar:
Bogus assert in OnDestroy
Check marks can be truncated in large font settings
Use pT to access GetSystemSettings, DrawMenuText, DrawBitmapDisabled, Draw3DCheckmark, DoPopupMenu, DoTrackPopupMenu, TakeFocus, GiveFocusBack, so they can be overridden
No hot-tracking if main window is not active
Top level items not painted inactive if app looses activation while drop down menu is displayed
Added Windows XP flat menus support
Drop-down menu doesn't close if clicked again (Windows XP only)
Menu item text and accelerator text too close with some settings
Keyboard can still access clipped menu items
Added support for hiding keyboard navigation indicators until Alt key is pressed (system setting)
Added AddIcon and ReplaceIcon variants for icon resources
Image size calculated differently in different places
Add support for 32-bit (alpha channel) bitmaps for Windows XP
Fixed width calculation for default menu items
 
CFrameWindowImpl:
AddSimpleReBarBandCtrl sets toolbar extended styles without preserving old ones
PrepareChevronMenu should not create menu items for buttons with TBSTATE_HIDDEN
TPM_VERPOSANIMATION will not be defined in atlframe.h if atlctrlw.h is included first
CreateSimpleToolBarCtrl - height might be too small if large font is used
PrepareChevronMenu uses TB_GETBUTTONTEXT, better use TB_GETBUTTONINFO
Chevron menu doesn't close if clicked again (Windows XP only)
Should check local classes for superclassing
Add support for 32-bit (alpha channel) bitmaps for Windows XP
 
Update UI:
UISetText can clear other menu item flags
CUpdateUI::UIUpdateState assigns value with |= instead of =
Added UISetDefault() and fix default state to work with menus
 
CString:
GetBuffer() and GetBufferSetLength() should return NULL in out-of-memory condition
Added missing methods: separate c-tors for LPCSTR and LPCWSTR, CollateNoCase, TrimRight and TrimLeft variants, Find variants, moved FormatV to public
Fix _IsValidString usage
FormatV incorrectly calculates buffer size (too big)
Usage of _ttoi causes problems with _ATL_MIN_CRT in VC7
 
CDC:
GetTabbedTextExtent() should return DWORD instead of BOOL
Add FillRect() that accept color index instead of a brush handle
DrawDragRect() leaks regions and a brush
Improved DitherBlt() - added brushes as arguments for used colors
Added DrawShadowText() (uses LoadLibrary/GetProcAddress to run on older Windows)
 
CListViewCtrl:
SetItemState should use LVM_SETITEMSTATE
SetItemCount should return a BOOL
 
CRichEditCtrl:
Added SetCharFormat() variant that accepts flags (for SCF_ALL)
CharFromPos() should pass a pointer to POINTL in lParam
GetTextRange() - should add Unicode variant for rich edit version >= 2
Added another FormatRange() that can accept a pointer to FORMATRANGE (needed for passing NULL to clear cache)
 
CHyperLink:
Allow overriding of Navigate and CalcLabelRect
Doesn't handle right or center alignment
 
CColorDialog:
Has static variables that were not initialized with _ATL_MIN_CRT
Fixed HookProc for ColorOK message - the message is not sent, but the hook proc is called directly
 
atlcrack.h:
MSG_WM_TIMER crack macro should cast to TIMERPROC instead of TIMERPROC*
Add cracked handlers for all new messages in Common Controls 6
 
atlapp.h:
Fixed problems with atlTraceUI with ATL7
#ifdefs for ATL7 were in the wrong place
 
atlctrls.h:
Add support in control classes for all new messages in Common Controls 6
 
CRecentDocumentList:
AtlCompactPath corrupts memory if filename is longer than requested compact size
ReadFromRegistry incorrectly checks for error when reading from registry
 
CSplitterWindow:
Incorrect calculation of middle position
3D border now drawn only if WS_EX_CLIENTEDGE is set
 
Printing:
Uses DWORD instead of an int for a job ID
CPrintJob::CancelPrintJob shouldn't have a return value
 
Misc:
CRegKey::QueryValue and SetValue are deprecated in ATL7
Added direct support for ATL7
Replace ScreenToClient and ClientToScreen with MapWindowPoints to support RTL layout
CFindFile::GetFilePath(LPTSTR...) returns path without the file name
MDI: Updating client edge in WM_WINDOWPOSCHANGING causes minimize/maximize/restore animation problems, use WM_WINDOWPOSCHANGED
Custom Draw: Added CCustomDraw::OnSubItemPrePaint() overrideable method
CFolderDialogImpl uses 'this' for BROWSEINFO.lParam instead of T*
CImageList::Destroy shouldn't use Detach()
ATL7 has its own AtlLoadString
CPropertySheet doesn't close when you press X button
Fixed problems for _U_STRINGorID and others that moved from atlbase.h to atlwin.h in ATL7
Add AtlMessageBox() that accepts either in-memory or resource strings
CScrollImpl: fixed bug with scrolling child windows
CPropertyPageImpl: Add new notification handlers to enable direct return values (use #ifdef _WTL_NEW_PAGE_NOTIFY_HANDLERS to use them)
Add AtlInitCommonControls() to simplify use
DDX: Fixed usage of the size of char arrays for DDX
CPageSetupDialog: changed usage of CWndProcThunk because of changes in ATL7
Fix confusing precedence in expressions
Removed forward declarations because default values for template arguments shouldn't be specified in two places (we don't need them anyway)
Win64: Fix /Wp64 warnings from 32-bit VC7 compiler caused by SDK headers
Fix direct usage of English strings (they can be #defined to something else now)
AtlGetCommCtrlVersion not defined if _ATL_DLL is in ATL 3.0 (and CmdBar is using it)
 
AppWizard:
Added manifest for Common Controls 6
Loading Rich Edit DLL should use HMODULE
Should not use atlimpl.cpp for ATL7
Added message handler prototypes to generated files
VERSION resource always has VALUE "OLESelfRegister" (now only for COM servers)
Added option for putting implementation in CPP files
d-tor for the thread manager class in MSDI project executed after the heap is destroyed
Wrong settings when changing to a dialog project and back (AppWizard 6.0 only)
Remove cut/copy/paste accelerators for form view and dialogs projects
Fix toolbar bitmaps so they are not transparent (problem with Windows XP flat menus only)
Used CMDICommandBarCtrl for MDI apps
Add symbols required for VC7 Class Wizard to recognize an ATL project
Changed default styles for the rebar, so it does look OK without CmdBar and with manifest
Added setup programs for both AppWizards
Remove ignored resource attributes: MOVEABLE, PURE, etc. (AppWizard 7.0 only)
Add call to DefWindowProc to WinMain to resolve possible problems if MSLU is used
 
Samples:
Updated toolbar bitmaps, added #ifdefs for ATL7, added manifest file for CommCtrl6, qualified _U_RECT with WTL namespace, updated use of deprecated CRegKey functions, added VC7 projects
Added Alpha sample
 
 
Changes Between WTL 3.1 and 3.0
 
New classes:
CPaneContainer - implements a window that provides a title bar and a close button (like Explorer)
CDialogResize - an MI class that allows resizing of dialogs (or any windows with child windows/controls)
CAxPropertyPageImpl - implements a property page that can host ActiveX controls
 
Fixes and enhancements:
CServerAppModule now clears m_hEventShutdown to avoid calling CloseHandle twice
 
CString:
operator += now leaves original string intact if it's out of memory
Fixed bad DWORD_PTR usage in TrimRight, TrimLeft, Replace, Remove
Removed dependencies on CRT for projects that don't use it
Insert - fixed string corruption in release builds
Added optional floating point formatting (for projects that use CRT)
 
CEdit and CRichEditCtrl: SetSelAll and SetSelNone had reversed implementation
 
atlres.h: Changed IDs so that they are compatible with MFC's afxres.h
 
Command Bar:
Added LoadMappedImages()
Changed handling of left and right arrow keys so that they don't close context menus
Add code to handle left/right arrow keys correctly on mirrored (RTL) systems
Removed handler that eats parent window's WM_SETTINGCHANGE
Fixed bitmap resource leak in Draw3DCheckmark
Fixed incorrect usage of CharLower in OnMenuChar
Fixed wrong color for the disabled items in hi-contrast mode
Added code to gray menu items if main window is inactive
Fixed keyboard mnemonic handling for IE 4
Fixed hook problems with multiple cmdbars in the same thread
Added support for radio menu items
Added support for disabled top-level menu items (also added in CFrameWindowImpl::PrepareChevronMenu)
Added keyboard shortcut (Alt+/) to invoke chevron menu
Added support to override menu item length in a derived class
 
CBitmapButton:
Bypassed BUTTON DefWindowProc for hover style so that the button doesn't take focus
Added BMPBTN_AUTOFIRE extended style
 
CDC:
Added _WTL_FORWARD_DECLARE_CSTRING define to allow usage of methods that accept CString
Fixed errors in GetTextFace and GetMenuItemString
Added GetCharWidth32
Added DrawIconEx method
 
CMenu:
Implement following missing methods:
    GetMenuDefaultItem
    GetMenuInfo
    GetMenuItemRect
    HiliteMenuItem
    IsMenu
    MenuItemFromPoint
    SetMenuDefaultItem
    SetMenuInfo
GetMenuString - fixed to include space for terminating NULL character in returning string
 
GDI and USER classes should destroy the GDI/USER objects in Attach if GDI/USER resource is managed
 
CFrameWindowImpl:
OnToolTipText shouldn't save tool tip text if it's not for a menu
AddSimpleReBarBandCtrl now adds chevron style only for toolbars with buttons
AddSimpleReBarBand(Ctrl) - calc band ID if not specified
 
CRecentDocumentList:
Fix - UpdateMenu deletes wrong menu item when the list is empty
Added code to allow restricting the number of characters displayed by MRU menu items
 
Update UI:
Added support for blocking accelerators for disabled items
Improved search code assuming there are no duplicate entries (and added checks for duplicates)
 
CSplitterWindow:
CSplitterWindowImpl should derive from CSplitterImpl<T , t_bVertical> to allow overriding of methods
Added single pane mode and SetSinglePaneMode/GetSinglePaneMode
Added right/bottom aligned resize mode using extended styles SPLIT_RIGHTALIGNED/SPLIT_BOTTOMALIGNED
 
atlcrack.h: Added handlers for following new messages:
    WM_APPCOMMAND
    WM_NCXBUTTONDOWN
    WM_NCXBUTTONUP
    WM_NCXBUTTONDBLCLK
    WM_XBUTTONDOWN
    WM_XBUTTONUP
    WM_XBUTTONDBLCLK
 
Win64:
Dialog return value should use DWLP_MSGRESULT and SetWindowLongPtr
CMenu::InsertMenu, AppendMenu, ModifyMenu should have UINT_PTR for the menu ID
Added appropriate type casts
CFrameWindowImpl::m_szAutoName - changed the size to fit the pointer value size
CListViewCtrl::SortItems should use LPARAM for user data instead of DWORD
 
Misc:
Added optional mask argument to all methods for setting extended styles
CMDIWindow::MDIRestore - fixed to send WM_MDIRESTORE instead of WM_MDIICONARRANGE
CListViewCtrl: Added SortItemsEx method
CToolBarCtrl::GetButtonInfo - fixed to return int instead of BOOL
Added CToolBarCtrl::SetButtonSize and SetBitmapSize that accept cx and cy instead of SIZE
Printing: Changed how GetNewDevModeForPage works (comments in code)
CFileDialogImpl::_OnTypeChange incorrectly calls pT->OnSelChange instead of pT->OnTypeChange
CMultiPaneStatusBarCtrl::GetPaneTipText - fixed to use index instead of and ID internally
CWinDataExchange: Added references to arguments of DoDataExchange, so there are no level 4 warning even if the map is empty
CPropertySheetWindow: Added new, IE 5.0 specific methods
CPropertyPageImpl: Added new, IE 5.0 specific methods
 
AppWizard:
added calls to RemoveMessageFilter and RemoveIdleHandler in CMainFrame::OnDestroy for COM server projects
added scroll bars for HTML view
CAppServerModule now handles -embedding as well as -automation
corrected code in CMainFrame::OnShowToolBar to correctly identify the toolbar in a rebar
dialog based app code now derives from CUpdateUI as public
 
