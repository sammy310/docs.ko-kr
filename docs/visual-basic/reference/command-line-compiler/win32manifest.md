---
title: -win32manifest
ms.date: 03/13/2018
helpviewer_keywords:
- /win32manifest compiler option [Visual Basic]
- win32manifest compiler option [Visual Basic]
- -win32manifest compiler option [Visual Basic]
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
ms.openlocfilehash: cef1e6c19e7fdd6fc9f42c8fc36008314ea80a80
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349140"
---
# <a name="-win32manifest-visual-basic"></a><span data-ttu-id="18399-102">-win32manifest (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18399-102">-win32manifest (Visual Basic)</span></span>
<span data-ttu-id="18399-103">프로젝트의 PE(포팅 가능한 실행 파일) 파일에 포함할 사용자 정의 Win32 애플리케이션 매니페스트 파일을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="18399-103">Identifies a user-defined Win32 application manifest file to be embedded into a project's portable executable (PE) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18399-104">구문</span><span class="sxs-lookup"><span data-stu-id="18399-104">Syntax</span></span>  
  
```console  
-win32manifest: fileName  
```  
  
## <a name="arguments"></a><span data-ttu-id="18399-105">인수</span><span class="sxs-lookup"><span data-stu-id="18399-105">Arguments</span></span>  
  
|<span data-ttu-id="18399-106">용어</span><span class="sxs-lookup"><span data-stu-id="18399-106">Term</span></span>|<span data-ttu-id="18399-107">정의</span><span class="sxs-lookup"><span data-stu-id="18399-107">Definition</span></span>|  
|---|---|  
|`fileName`|<span data-ttu-id="18399-108">The path of the custom manifest file.</span><span class="sxs-lookup"><span data-stu-id="18399-108">The path of the custom manifest file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18399-109">주의</span><span class="sxs-lookup"><span data-stu-id="18399-109">Remarks</span></span>  
 <span data-ttu-id="18399-110">By default, the Visual Basic compiler embeds an application manifest that specifies a requested execution level of asInvoker.</span><span class="sxs-lookup"><span data-stu-id="18399-110">By default, the Visual Basic compiler embeds an application manifest that specifies a requested execution level of asInvoker.</span></span> <span data-ttu-id="18399-111">It creates the manifest in the same folder in which the executable file is built, typically the bin\Debug or bin\Release folder when you use Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="18399-111">It creates the manifest in the same folder in which the executable file is built, typically the bin\Debug or bin\Release folder when you use Visual Studio.</span></span> <span data-ttu-id="18399-112">If you want to supply a custom manifest, for example to specify a requested execution level of highestAvailable or requireAdministrator, use this option to specify the name of the file.</span><span class="sxs-lookup"><span data-stu-id="18399-112">If you want to supply a custom manifest, for example to specify a requested execution level of highestAvailable or requireAdministrator, use this option to specify the name of the file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="18399-113">This option and the [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) option are mutually exclusive.</span><span class="sxs-lookup"><span data-stu-id="18399-113">This option and the [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) option are mutually exclusive.</span></span> <span data-ttu-id="18399-114">If you try to use both options in the same command line, you will get a build error.</span><span class="sxs-lookup"><span data-stu-id="18399-114">If you try to use both options in the same command line, you will get a build error.</span></span>  
  
 <span data-ttu-id="18399-115">요청된 실행 수준을 지정하는 애플리케이션 매니페스트가 없는 애플리케이션은 Windows Vista의 사용자 계정 컨트롤 기능 아래에서 파일/레지스트리 가상화의 적용을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="18399-115">An application that has no application manifest that specifies a requested execution level will be subject to file/registry virtualization under the User Account Control feature in Windows Vista.</span></span> <span data-ttu-id="18399-116">가상화에 대한 자세한 내용은 [ClickOnce Deployment on Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista)(Windows Vista의 ClickOnce 배포)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="18399-116">For more information about virtualization, see [ClickOnce Deployment on Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span></span>  
  
 <span data-ttu-id="18399-117">Your application will be subject to virtualization if either of the following conditions is true:</span><span class="sxs-lookup"><span data-stu-id="18399-117">Your application will be subject to virtualization if either of the following conditions is true:</span></span>  
  
1. <span data-ttu-id="18399-118">You use the `-nowin32manifest` option and you do not provide a manifest in a later build step or as part of a Windows Resource (.res) file by using the `-win32resource` option.</span><span class="sxs-lookup"><span data-stu-id="18399-118">You use the `-nowin32manifest` option and you do not provide a manifest in a later build step or as part of a Windows Resource (.res) file by using the `-win32resource` option.</span></span>  
  
2. <span data-ttu-id="18399-119">요청한 실행 수준을 지정하지 않는 사용자 지정 매니페스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="18399-119">You provide a custom manifest that does not specify a requested execution level.</span></span>  
  
 <span data-ttu-id="18399-120">Visual Studio는 기본 .manifest 파일을 만들고 이를 실행 파일과 함께 debug 및 release 디렉터리에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="18399-120">Visual Studio creates a default .manifest file and stores it in the debug and release directories alongside the executable file.</span></span> <span data-ttu-id="18399-121">You can view or edit the default app.manifest file by clicking **View UAC Settings** on the **Application** tab in the Project Designer.</span><span class="sxs-lookup"><span data-stu-id="18399-121">You can view or edit the default app.manifest file by clicking **View UAC Settings** on the **Application** tab in the Project Designer.</span></span> <span data-ttu-id="18399-122">자세한 내용은 [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="18399-122">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="18399-123">You can provide the application manifest as a custom post-build step or as part of a Win32 resource file by using the `-nowin32manifest` option.</span><span class="sxs-lookup"><span data-stu-id="18399-123">You can provide the application manifest as a custom post-build step or as part of a Win32 resource file by using the `-nowin32manifest` option.</span></span> <span data-ttu-id="18399-124">애플리케이션이 Windows Vista에서 파일 또는 레지스트리 가상화의 적용을 받도록 하려면 동일한 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="18399-124">Use that same option if you want your application to be subject to file or registry virtualization on Windows Vista.</span></span> <span data-ttu-id="18399-125">This will prevent the compiler from creating and embedding a default manifest in the PE file.</span><span class="sxs-lookup"><span data-stu-id="18399-125">This will prevent the compiler from creating and embedding a default manifest in the PE file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18399-126">예제</span><span class="sxs-lookup"><span data-stu-id="18399-126">Example</span></span>  
 <span data-ttu-id="18399-127">The following example shows the default manifest that the Visual Basic compiler inserts into a PE.</span><span class="sxs-lookup"><span data-stu-id="18399-127">The following example shows the default manifest that the Visual Basic compiler inserts into a PE.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="18399-128">The compiler inserts a standard application name MyApplication.app into the manifest XML.</span><span class="sxs-lookup"><span data-stu-id="18399-128">The compiler inserts a standard application name MyApplication.app into the manifest XML.</span></span> <span data-ttu-id="18399-129">이는 Windows Server 2003 서비스 팩 3에서 애플리케이션을 실행하기 위한 해결 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="18399-129">This is a workaround to enable applications to run on Windows Server 2003 Service Pack 3.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
  <assemblyIdentity version="1.0.0.0" name="MyApplication.app"/>  
  <trustInfo xmlns="urn:schemas-microsoft-com:asm.v2">  
    <security>  
      <requestedPrivileges xmlns="urn:schemas-microsoft-com:asm.v3">  
        <requestedExecutionLevel level="asInvoker"/>  
      </requestedPrivileges>  
    </security>  
  </trustInfo>  
</assembly>  
```  
  
## <a name="see-also"></a><span data-ttu-id="18399-130">참조</span><span class="sxs-lookup"><span data-stu-id="18399-130">See also</span></span>

- [<span data-ttu-id="18399-131">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="18399-131">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="18399-132">-nowin32manifest (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18399-132">-nowin32manifest (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)
