---
title: '방법: IIS 5.0 및 IIS 6.0을 구성하여 WPF 애플리케이션 배포'
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- MIME types [WPF], registering
- adjusting content expiration setting [WPF]
- registering file extensions [WPF]
- deploying applications [WPF]
- applications [WPF], deploying
- Web servers [WPF], configuring to deploy WPF applications
- configuring Web servers to deploy WPF applications [WPF]
- content expiration setting [WPF], adjusting
- file extensions [WPF], registering
- registering MIME types [WPF]
ms.assetid: c6e8c2cb-9ba2-4e75-a0d5-180ec9639433
ms.openlocfilehash: d557ac6cd380edcbc93b5315f6356697817274bf
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740411"
---
# <a name="how-to-configure-iis-50-and-iis-60-to-deploy-wpf-applications"></a><span data-ttu-id="2a1b5-102">방법: IIS 5.0 및 IIS 6.0을 구성하여 WPF 애플리케이션 배포</span><span class="sxs-lookup"><span data-stu-id="2a1b5-102">How to: Configure IIS 5.0 and IIS 6.0 to Deploy WPF Applications</span></span>

<span data-ttu-id="2a1b5-103">적절 한 MIME (인터넷 메일 확장) 형식으로 구성 된 대부분의 웹 서버에서 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a1b5-103">You can deploy a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application from most Web servers, as long as they are configured with the appropriate Multipurpose Internet Mail Extensions (MIME) types.</span></span> <span data-ttu-id="2a1b5-104">기본적으로 Microsoft 인터넷 정보 서비스 (IIS) 7.0는 이러한 MIME 형식으로 구성 되지만 Microsoft 인터넷 정보 서비스 (IIS) 5.0 및 Microsoft 인터넷 정보 서비스 (IIS) 6.0는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2a1b5-104">By default, Microsoft Internet Information Services (IIS) 7.0 is configured with these MIME types, but Microsoft Internet Information Services (IIS) 5.0 and Microsoft Internet Information Services (IIS) 6.0 are not.</span></span>

<span data-ttu-id="2a1b5-105">이 항목에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램을 배포 하기 위해 Microsoft 인터넷 정보 서비스 (IIS) 5.0 및 Microsoft 인터넷 정보 서비스 (IIS) 6.0를 구성 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a1b5-105">This topic describes how to configure Microsoft Internet Information Services (IIS) 5.0 and Microsoft Internet Information Services (IIS) 6.0 to deploy [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications.</span></span>

> [!NOTE]
> <span data-ttu-id="2a1b5-106">레지스트리에서 *UserAgent* 문자열을 확인 하 여 시스템에 .NET Framework 설치 되어 있는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a1b5-106">You can check the *UserAgent* string in the registry to determine whether a system has .NET Framework installed.</span></span> <span data-ttu-id="2a1b5-107">*UserAgent* 문자열을 검사 하 여 .NET Framework가 시스템에 설치 되어 있는지 여부를 확인 하는 스크립트 및 세부 정보는 [.NET Framework 3.0가 설치 되어 있는지 검색](how-to-detect-whether-the-net-framework-3-0-is-installed.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2a1b5-107">For details and a script that examines the *UserAgent* string to determine whether .NET Framework is installed on a system, see [Detect Whether the .NET Framework 3.0 Is Installed](how-to-detect-whether-the-net-framework-3-0-is-installed.md).</span></span>

<a name="content_expiration"></a>

## <a name="adjust-the-content-expiration-setting"></a><span data-ttu-id="2a1b5-108">콘텐츠 만료 설정 조정</span><span class="sxs-lookup"><span data-stu-id="2a1b5-108">Adjust the Content Expiration Setting</span></span>

<span data-ttu-id="2a1b5-109">콘텐츠 만료 설정을 1분으로 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a1b5-109">You should adjust the content expiration setting to 1 minute.</span></span> <span data-ttu-id="2a1b5-110">다음 절차에서는 IIS를 사용 하 여이 작업을 수행 하는 방법을 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a1b5-110">The following procedure outlines how to do this with IIS.</span></span>

1. <span data-ttu-id="2a1b5-111">**시작** 메뉴를 클릭하고 **관리 도구**를 가리킨 후 **IIS(인터넷 정보 서비스) 관리자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2a1b5-111">Click the **Start** menu, point to **Administrative Tools**, and click **Internet Information Services (IIS) Manager**.</span></span> <span data-ttu-id="2a1b5-112">명령줄에서도 “%SystemRoot%\system32\inetsrv\iis.msc”로 이 애플리케이션을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a1b5-112">You can also launch this application from the command line with "%SystemRoot%\system32\inetsrv\iis.msc".</span></span>

2. <span data-ttu-id="2a1b5-113">**기본 웹 사이트** 노드를 찾을 때까지 IIS 트리를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a1b5-113">Expand the IIS tree until you find the **Default Web site** node.</span></span>

3. <span data-ttu-id="2a1b5-114">**기본 웹 사이트**를 마우스 오른쪽 단추로 클릭하고 컨텍스트 메뉴에서 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2a1b5-114">Right-click **Default Web site** and select **Properties** from the context menu.</span></span>

4. <span data-ttu-id="2a1b5-115">**HTTP 헤더** 탭을 선택하고 “콘텐츠 만료 사용”을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2a1b5-115">Select the **HTTP Headers** tab and click "Enable Content Expiration".</span></span>

5. <span data-ttu-id="2a1b5-116">1분 후에 만료하도록 콘텐츠를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2a1b5-116">Set the content to expire after 1 minute.</span></span>

<a name="register_mime_types"></a>

## <a name="register-mime-types-and-file-extensions"></a><span data-ttu-id="2a1b5-117">MIME 형식과 파일 확장명 등록</span><span class="sxs-lookup"><span data-stu-id="2a1b5-117">Register MIME Types and File Extensions</span></span>

<span data-ttu-id="2a1b5-118">클라이언트 시스템의 브라우저에서 올바른 처리기를 로드할 수 있도록 여러 MIME 형식 및 파일 확장명을 등록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a1b5-118">You must register several MIME types and file extensions so that the browser on the client's system can load the correct handler.</span></span> <span data-ttu-id="2a1b5-119">다음 형식을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a1b5-119">You need to add the following types:</span></span>

|<span data-ttu-id="2a1b5-120">확장명</span><span class="sxs-lookup"><span data-stu-id="2a1b5-120">Extension</span></span>|<span data-ttu-id="2a1b5-121">MIME 형식</span><span class="sxs-lookup"><span data-stu-id="2a1b5-121">MIME Type</span></span>|
|---------------|---------------|
|<span data-ttu-id="2a1b5-122">.manifest</span><span class="sxs-lookup"><span data-stu-id="2a1b5-122">.manifest</span></span>|<span data-ttu-id="2a1b5-123">application/manifest</span><span class="sxs-lookup"><span data-stu-id="2a1b5-123">application/manifest</span></span>|
|<span data-ttu-id="2a1b5-124">.xaml</span><span class="sxs-lookup"><span data-stu-id="2a1b5-124">.xaml</span></span>|<span data-ttu-id="2a1b5-125">application/xaml+xml</span><span class="sxs-lookup"><span data-stu-id="2a1b5-125">application/xaml+xml</span></span>|
|<span data-ttu-id="2a1b5-126">.application</span><span class="sxs-lookup"><span data-stu-id="2a1b5-126">.application</span></span>|<span data-ttu-id="2a1b5-127">application/x-ms-application</span><span class="sxs-lookup"><span data-stu-id="2a1b5-127">application/x-ms-application</span></span>|
|<span data-ttu-id="2a1b5-128">.xbap</span><span class="sxs-lookup"><span data-stu-id="2a1b5-128">.xbap</span></span>|<span data-ttu-id="2a1b5-129">application/x-ms-xbap</span><span class="sxs-lookup"><span data-stu-id="2a1b5-129">application/x-ms-xbap</span></span>|
|<span data-ttu-id="2a1b5-130">.deploy</span><span class="sxs-lookup"><span data-stu-id="2a1b5-130">.deploy</span></span>|<span data-ttu-id="2a1b5-131">application/octet-stream</span><span class="sxs-lookup"><span data-stu-id="2a1b5-131">application/octet-stream</span></span>|
|<span data-ttu-id="2a1b5-132">.xps</span><span class="sxs-lookup"><span data-stu-id="2a1b5-132">.xps</span></span>|<span data-ttu-id="2a1b5-133">application/vnd.ms-xpsdocument</span><span class="sxs-lookup"><span data-stu-id="2a1b5-133">application/vnd.ms-xpsdocument</span></span>|

> [!NOTE]
> <span data-ttu-id="2a1b5-134">클라이언트 시스템에는 MIME 형식 또는 파일 확장명을 등록할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2a1b5-134">You do not need to register MIME types or file extensions on client systems.</span></span> <span data-ttu-id="2a1b5-135">Microsoft .NET Framework를 설치할 때 자동으로 등록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a1b5-135">They are registered automatically when you install Microsoft .NET Framework.</span></span>

<span data-ttu-id="2a1b5-136">다음 VBScript (Microsoft Visual Basic Scripting Edition) 샘플에서는 IIS에 필요한 MIME 형식을 자동으로 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a1b5-136">The following Microsoft Visual Basic Scripting Edition (VBScript) sample automatically adds the necessary MIME types to IIS.</span></span> <span data-ttu-id="2a1b5-137">스크립트를 사용하려면 서버에서 .vbs 파일을 코드에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="2a1b5-137">To use the script, copy the code to a .vbs file on your server.</span></span> <span data-ttu-id="2a1b5-138">그런 다음 명령줄에서 파일을 실행 하거나 Microsoft Windows 탐색기에서 파일을 두 번 클릭 하 여 스크립트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a1b5-138">Then, run the script by running the file from the command line or double-clicking the file in Microsoft Windows Explorer.</span></span>

```vb
' This script adds the necessary Windows Presentation Foundation MIME types
' to an IIS Server.
' To use this script, just double-click or execute it from a command line.
' Running this script multiple times results in multiple entries in the IIS MimeMap.

Dim MimeMapObj, MimeMapArray, MimeTypesToAddArray, WshShell, oExec
Const ADS_PROPERTY_UPDATE = 2

' Set the MIME types to be added
MimeTypesToAddArray = Array(".manifest", "application/manifest", ".xaml", _
    "application/xaml+xml", ".application", "application/x-ms-application", _
    ".deploy", "application/octet-stream", ".xbap", "application/x-ms-xbap", _
    ".xps", "application/vnd.ms-xpsdocument")

' Get the MimeMap object
Set MimeMapObj = GetObject("IIS://LocalHost/MimeMap")

' Call AddMimeType for every pair of extension/MIME type
For counter = 0 to UBound(MimeTypesToAddArray) Step 2
    AddMimeType MimeTypesToAddArray(counter), MimeTypesToAddArray(counter+1)
Next

' Create a Shell object
Set WshShell = CreateObject("WScript.Shell")

' Stop and Start the IIS Service
Set oExec = WshShell.Exec("net stop w3svc")
Do While oExec.Status = 0
    WScript.Sleep 100
Loop

Set oExec = WshShell.Exec("net start w3svc")
Do While oExec.Status = 0
    WScript.Sleep 100
Loop

Set oExec = Nothing

' Report status to user
WScript.Echo "Windows Presentation Foundation MIME types have been registered."

' AddMimeType Sub
Sub AddMimeType (Ext, MType)

    ' Get the mappings from the MimeMap property.
    MimeMapArray = MimeMapObj.GetEx("MimeMap")

    ' Add a new mapping.
    i = UBound(MimeMapArray) + 1
    ReDim Preserve MimeMapArray(i)
    Set MimeMapArray(i) = CreateObject("MimeMap")
    MimeMapArray(i).Extension = Ext
    MimeMapArray(i).MimeType = MType
    MimeMapObj.PutEx ADS_PROPERTY_UPDATE, "MimeMap", MimeMapArray
    MimeMapObj.SetInfo

End Sub
```

> [!NOTE]
> <span data-ttu-id="2a1b5-139">이 스크립트를 여러 번 실행 하면 Microsoft 인터넷 정보 서비스 (IIS) 5.0 또는 Microsoft 인터넷 정보 서비스 (IIS) 6.0 메타 베이스에 여러 MIME 맵 항목이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a1b5-139">Running this script multiple times creates multiple MIME map entries in the Microsoft Internet Information Services (IIS) 5.0 or Microsoft Internet Information Services (IIS) 6.0 metabase.</span></span>

<span data-ttu-id="2a1b5-140">이 스크립트를 실행 한 후에는 Microsoft 인터넷 정보 서비스 (IIS) 5.0 또는 microsoft 인터넷 정보 서비스 (IIS) 6.0 MMC (microsoft Management Console)에서 추가 MIME 형식이 표시 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a1b5-140">After you have run this script, you may not see additional MIME types from the Microsoft Internet Information Services (IIS) 5.0 or Microsoft Internet Information Services (IIS) 6.0 Microsoft Management Console (MMC).</span></span> <span data-ttu-id="2a1b5-141">그러나 이러한 MIME 형식은 Microsoft 인터넷 정보 서비스 (IIS) 5.0 또는 Microsoft 인터넷 정보 서비스 (IIS) 6.0 메타 베이스에 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2a1b5-141">However, these MIME types have been added to the Microsoft Internet Information Services (IIS) 5.0 or Microsoft Internet Information Services (IIS) 6.0 metabase.</span></span> <span data-ttu-id="2a1b5-142">다음 스크립트는 Microsoft 인터넷 정보 서비스 (IIS) 5.0 또는 Microsoft 인터넷 정보 서비스 (IIS) 6.0 메타 베이스에 모든 MIME 형식을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a1b5-142">The following script will display all the MIME types in the Microsoft Internet Information Services (IIS) 5.0 or Microsoft Internet Information Services (IIS) 6.0 metabase.</span></span>

```vb
' This script lists the MIME types for an IIS Server.
' To use this script, just double-click or execute it from a command line
' by calling cscript.exe

dim mimeMapEntry, allMimeMaps

' Get the MimeMap object.
Set mimeMapEntry = GetObject("IIS://localhost/MimeMap")
allMimeMaps = mimeMapEntry.GetEx("MimeMap")

' Display the mappings in the table.
For Each mimeMap In allMimeMaps
    WScript.Echo(mimeMap.MimeType & " (" & mimeMap.Extension + ")")
Next
```

<span data-ttu-id="2a1b5-143">스크립트를 `.vbs` 파일로 저장하고(예: `DiscoverIISMimeTypes.vbs`) 다음 명령을 사용하여 명령 프롬프트에서 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2a1b5-143">Save the script as a `.vbs` file (for example, `DiscoverIISMimeTypes.vbs`) and run it from the command prompt using the following command:</span></span>

```console
cscript DiscoverIISMimeTypes.vbs
```
