---
title: -nowin32manifest(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /nowin32manifest
helpviewer_keywords:
- nowin32manifest compiler option [C#]
- -nowin32manifest compiler option [C#]
- /nowin32manifest compiler option [C#]
ms.assetid: 6f06365b-b87b-46a2-b187-b3bfeaf4862d
ms.openlocfilehash: 8820410bfdbce2f9986605f37af4d14957471126
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "69602721"
---
# <a name="-nowin32manifest-c-compiler-options"></a><span data-ttu-id="e2056-102">-nowin32manifest(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="e2056-102">-nowin32manifest (C# Compiler Options)</span></span>
<span data-ttu-id="e2056-103">**-nowin32manifest** 옵션을 사용하면 실행 파일에 애플리케이션 매니페스트를 포함하지 않도록 컴파일러에 지시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2056-103">Use the **-nowin32manifest** option to instruct the compiler not to embed any application manifest into the executable file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2056-104">구문</span><span class="sxs-lookup"><span data-stu-id="e2056-104">Syntax</span></span>  
  
```console  
-nowin32manifest  
```  
  
## <a name="remarks"></a><span data-ttu-id="e2056-105">설명</span><span class="sxs-lookup"><span data-stu-id="e2056-105">Remarks</span></span>  
 <span data-ttu-id="e2056-106">이 옵션을 사용하는 경우 Win32 리소스 파일에서 또는 이후 빌드 단계 중에 애플리케이션 매니페스트를 제공하지 않으면 Windows Vista에서 애플리케이션에 가상화가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2056-106">When this option is used, the application will be subject to virtualization on Windows Vista unless you provide an application manifest in a Win32 Resource file or during a later build step.</span></span>  
  
 <span data-ttu-id="e2056-107">Visual Studio의 **애플리케이션 속성** 페이지에 있는 **매니페스트** 드롭다운 목록에서 **매니페스트 없이 애플리케이션 만들기** 옵션을 선택하여 이 옵션을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e2056-107">In Visual Studio, set this option in the **Application Property** page by selecting the **Create Application Without a Manifest** option in the **Manifest** drop down list.</span></span> <span data-ttu-id="e2056-108">자세한 내용은 [프로젝트 디자이너, 애플리케이션 페이지(C#)](/visualstudio/ide/reference/application-page-project-designer-csharp)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e2056-108">For more information, see [Application Page, Project Designer (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).</span></span>  
  
 <span data-ttu-id="e2056-109">매니페스트 생성에 대한 자세한 내용은 [-win32manifest(C# 컴파일러 옵션)](./win32manifest-compiler-option.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e2056-109">For more information about manifest creation, see [-win32manifest (C# Compiler Options)](./win32manifest-compiler-option.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2056-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e2056-110">See also</span></span>

- [<span data-ttu-id="e2056-111">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="e2056-111">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="e2056-112">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="e2056-112">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
