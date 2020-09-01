---
description: -nowin32manifest(C# 컴파일러 옵션)
title: -nowin32manifest(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /nowin32manifest
helpviewer_keywords:
- nowin32manifest compiler option [C#]
- -nowin32manifest compiler option [C#]
- /nowin32manifest compiler option [C#]
ms.assetid: 6f06365b-b87b-46a2-b187-b3bfeaf4862d
ms.openlocfilehash: 8514ab5b118e320d456d1b7367fab3b463c3607a
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125061"
---
# <a name="-nowin32manifest-c-compiler-options"></a><span data-ttu-id="daaee-103">-nowin32manifest(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="daaee-103">-nowin32manifest (C# Compiler Options)</span></span>
<span data-ttu-id="daaee-104">**-nowin32manifest** 옵션을 사용하면 실행 파일에 애플리케이션 매니페스트를 포함하지 않도록 컴파일러에 지시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daaee-104">Use the **-nowin32manifest** option to instruct the compiler not to embed any application manifest into the executable file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="daaee-105">구문</span><span class="sxs-lookup"><span data-stu-id="daaee-105">Syntax</span></span>  
  
```console  
-nowin32manifest  
```  
  
## <a name="remarks"></a><span data-ttu-id="daaee-106">설명</span><span class="sxs-lookup"><span data-stu-id="daaee-106">Remarks</span></span>  
 <span data-ttu-id="daaee-107">이 옵션을 사용하는 경우 Win32 리소스 파일에서 또는 이후 빌드 단계 중에 애플리케이션 매니페스트를 제공하지 않으면 Windows Vista에서 애플리케이션에 가상화가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="daaee-107">When this option is used, the application will be subject to virtualization on Windows Vista unless you provide an application manifest in a Win32 Resource file or during a later build step.</span></span>  
  
 <span data-ttu-id="daaee-108">Visual Studio의 **애플리케이션 속성** 페이지에 있는 **매니페스트** 드롭다운 목록에서 **매니페스트 없이 애플리케이션 만들기** 옵션을 선택하여 이 옵션을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="daaee-108">In Visual Studio, set this option in the **Application Property** page by selecting the **Create Application Without a Manifest** option in the **Manifest** drop down list.</span></span> <span data-ttu-id="daaee-109">자세한 내용은 [프로젝트 디자이너, 애플리케이션 페이지(C#)](/visualstudio/ide/reference/application-page-project-designer-csharp)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="daaee-109">For more information, see [Application Page, Project Designer (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).</span></span>  
  
 <span data-ttu-id="daaee-110">매니페스트 생성에 대한 자세한 내용은 [-win32manifest(C# 컴파일러 옵션)](./win32manifest-compiler-option.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="daaee-110">For more information about manifest creation, see [-win32manifest (C# Compiler Options)](./win32manifest-compiler-option.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daaee-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="daaee-111">See also</span></span>

- [<span data-ttu-id="daaee-112">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="daaee-112">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="daaee-113">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="daaee-113">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
