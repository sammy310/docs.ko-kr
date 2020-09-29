---
title: -win32manifest
ms.date: 03/13/2018
helpviewer_keywords:
- /win32manifest compiler option [Visual Basic]
- win32manifest compiler option [Visual Basic]
- -win32manifest compiler option [Visual Basic]
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
ms.openlocfilehash: f8329ce2e7597f802d75ec85a580f1a3bd5cfc97
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91098880"
---
# <a name="-win32manifest-visual-basic"></a><span data-ttu-id="9959e-102">-win32manifest(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9959e-102">-win32manifest (Visual Basic)</span></span>

<span data-ttu-id="9959e-103">프로젝트의 PE(포팅 가능한 실행 파일) 파일에 포함할 사용자 정의 Win32 애플리케이션 매니페스트 파일을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="9959e-103">Identifies a user-defined Win32 application manifest file to be embedded into a project's portable executable (PE) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9959e-104">구문</span><span class="sxs-lookup"><span data-stu-id="9959e-104">Syntax</span></span>  
  
```console  
-win32manifest: fileName  
```  
  
## <a name="arguments"></a><span data-ttu-id="9959e-105">인수</span><span class="sxs-lookup"><span data-stu-id="9959e-105">Arguments</span></span>  
  
|<span data-ttu-id="9959e-106">용어</span><span class="sxs-lookup"><span data-stu-id="9959e-106">Term</span></span>|<span data-ttu-id="9959e-107">정의</span><span class="sxs-lookup"><span data-stu-id="9959e-107">Definition</span></span>|  
|---|---|  
|`fileName`|<span data-ttu-id="9959e-108">사용자 지정 매니페스트 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="9959e-108">The path of the custom manifest file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9959e-109">설명</span><span class="sxs-lookup"><span data-stu-id="9959e-109">Remarks</span></span>  

 <span data-ttu-id="9959e-110">기본적으로 Visual Basic 컴파일러는 asInvoker의 요청된 실행 수준을 지정하는 애플리케이션 매니페스트를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9959e-110">By default, the Visual Basic compiler embeds an application manifest that specifies a requested execution level of asInvoker.</span></span> <span data-ttu-id="9959e-111">Visual Studio를 사용할 때 일반적으로 bin\Debug 또는 bin\Release 폴더와 같이 실행 파일이 빌드되는 동일한 폴더에 매니페스트가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9959e-111">It creates the manifest in the same folder in which the executable file is built, typically the bin\Debug or bin\Release folder when you use Visual Studio.</span></span> <span data-ttu-id="9959e-112">예를 들어 highestAvailable 또는 requireAdministrator의 요청된 실행 수준을 지정하기 위해 사용자 지정 매니페스트를 제공하려면 이 옵션을 사용하여 파일 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9959e-112">If you want to supply a custom manifest, for example to specify a requested execution level of highestAvailable or requireAdministrator, use this option to specify the name of the file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9959e-113">이 옵션과 [-win32resource](win32resource.md) 옵션은 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9959e-113">This option and the [-win32resource](win32resource.md) option are mutually exclusive.</span></span> <span data-ttu-id="9959e-114">같은 명령줄에서 두 옵션을 모두 사용하려고 하면 빌드 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="9959e-114">If you try to use both options in the same command line, you will get a build error.</span></span>  
  
 <span data-ttu-id="9959e-115">요청된 실행 수준을 지정하는 애플리케이션 매니페스트가 없는 애플리케이션은 Windows Vista의 사용자 계정 컨트롤 기능 아래에서 파일/레지스트리 가상화의 적용을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="9959e-115">An application that has no application manifest that specifies a requested execution level will be subject to file/registry virtualization under the User Account Control feature in Windows Vista.</span></span> <span data-ttu-id="9959e-116">가상화에 대한 자세한 내용은 [ClickOnce Deployment on Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista)(Windows Vista의 ClickOnce 배포)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9959e-116">For more information about virtualization, see [ClickOnce Deployment on Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span></span>  
  
 <span data-ttu-id="9959e-117">다음 조건 중 하나라도 true인 경우 애플리케이션에 가상화가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9959e-117">Your application will be subject to virtualization if either of the following conditions is true:</span></span>  
  
1. <span data-ttu-id="9959e-118">사용자는 `-nowin32manifest` 옵션을 사용하며, `-win32resource` 옵션을 사용하여 나중 빌드 단계 또는 Windows Resource(.res) 파일의 일부로 매니페스트를 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9959e-118">You use the `-nowin32manifest` option and you do not provide a manifest in a later build step or as part of a Windows Resource (.res) file by using the `-win32resource` option.</span></span>  
  
2. <span data-ttu-id="9959e-119">요청한 실행 수준을 지정하지 않는 사용자 지정 매니페스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9959e-119">You provide a custom manifest that does not specify a requested execution level.</span></span>  
  
 <span data-ttu-id="9959e-120">Visual Studio는 기본 .manifest 파일을 만들고 이를 실행 파일과 함께 debug 및 release 디렉터리에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="9959e-120">Visual Studio creates a default .manifest file and stores it in the debug and release directories alongside the executable file.</span></span> <span data-ttu-id="9959e-121">프로젝트 디자이너의 **애플리케이션** 탭에서 **UAC 설정 보기**를 클릭하여 기본 app.manifest 파일을 보거나 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9959e-121">You can view or edit the default app.manifest file by clicking **View UAC Settings** on the **Application** tab in the Project Designer.</span></span> <span data-ttu-id="9959e-122">자세한 내용은 [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9959e-122">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="9959e-123">`-nowin32manifest` 옵션을 사용하여 애플리케이션 매니페스트를 사용자 지정 빌드 후 단계 또는 Win32 리소스 파일의 일부로 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9959e-123">You can provide the application manifest as a custom post-build step or as part of a Win32 resource file by using the `-nowin32manifest` option.</span></span> <span data-ttu-id="9959e-124">애플리케이션이 Windows Vista에서 파일 또는 레지스트리 가상화의 적용을 받도록 하려면 동일한 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9959e-124">Use that same option if you want your application to be subject to file or registry virtualization on Windows Vista.</span></span> <span data-ttu-id="9959e-125">이렇게 하면 컴파일러가 PE 파일에 기본 매니페스트를 만들고 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9959e-125">This will prevent the compiler from creating and embedding a default manifest in the PE file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9959e-126">예제</span><span class="sxs-lookup"><span data-stu-id="9959e-126">Example</span></span>  

 <span data-ttu-id="9959e-127">다음 예제에서는 Basic C# 컴파일러가 PE에 삽입하는 기본 매니페스트를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="9959e-127">The following example shows the default manifest that the Visual Basic compiler inserts into a PE.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9959e-128">컴파일러는 표준 애플리케이션 이름 "MyApplication.app"을 매니페스트 XML에 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="9959e-128">The compiler inserts a standard application name MyApplication.app into the manifest XML.</span></span> <span data-ttu-id="9959e-129">이는 Windows Server 2003 서비스 팩 3에서 애플리케이션을 실행하기 위한 해결 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="9959e-129">This is a workaround to enable applications to run on Windows Server 2003 Service Pack 3.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9959e-130">참조</span><span class="sxs-lookup"><span data-stu-id="9959e-130">See also</span></span>

- [<span data-ttu-id="9959e-131">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="9959e-131">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="9959e-132">-nowin32manifest(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9959e-132">-nowin32manifest (Visual Basic)</span></span>](nowin32manifest.md)
