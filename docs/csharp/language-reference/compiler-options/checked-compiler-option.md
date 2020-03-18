---
title: -checked(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /checked
helpviewer_keywords:
- checked compiler option [C#]
- -checked compiler option [C#]
- /checked compiler option [C#]
ms.assetid: fb7475d3-e6a6-4e6d-b86c-69e7a74c854b
ms.openlocfilehash: cb4dbadfa4efd0750ffd3dea88a3f661e2f85a8e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173772"
---
# <a name="-checked-c-compiler-options"></a><span data-ttu-id="e374c-102">-checked(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="e374c-102">-checked (C# Compiler Options)</span></span>
<span data-ttu-id="e374c-103">**-checked** 옵션은 데이터 형식 범위를 벗어나고 [checked](../keywords/checked.md) 또는 [unchecked](../keywords/unchecked.md) 키워드의 범위 내에 없는 값을 생성하는 정수 산술 문이 런타임 예외를 일으킬지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e374c-103">The **-checked** option specifies whether an integer arithmetic statement that results in a value that is outside the range of the data type, and that is not in the scope of a [checked](../keywords/checked.md) or [unchecked](../keywords/unchecked.md) keyword, causes a run-time exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e374c-104">구문</span><span class="sxs-lookup"><span data-stu-id="e374c-104">Syntax</span></span>  
  
```console  
-checked[+ | -]  
```  
  
## <a name="remarks"></a><span data-ttu-id="e374c-105">설명</span><span class="sxs-lookup"><span data-stu-id="e374c-105">Remarks</span></span>  
 <span data-ttu-id="e374c-106">`checked` 또는 `unchecked` 키워드의 범위 내에 있는 정수 산술 문에는 **-checked** 옵션이 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e374c-106">An integer arithmetic statement that is in the scope of a `checked` or `unchecked` keyword is not subject to the effect of the **-checked** option.</span></span>  
  
 <span data-ttu-id="e374c-107">`checked` 또는 `unchecked` 키워드의 범위에 없는 정수 산술 문이 데이터 형식 범위를 벗어난 값을 생성하고 **-checked+** (또는 **-checked**)가 컴파일에서 사용될 경우 해당 명령문은 런타임에 예외를 일으킵니다.</span><span class="sxs-lookup"><span data-stu-id="e374c-107">If an integer arithmetic statement that is not in the scope of a `checked` or `unchecked` keyword results in a value outside the range of the data type, and **-checked+** (or **-checked**) is used in the compilation, that statement causes an exception at run time.</span></span> <span data-ttu-id="e374c-108">**-checked-** 가 컴파일에 사용될 경우 해당 문은 런타임에 예외를 일으키지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e374c-108">If **-checked-** is used in the compilation, that statement does not cause an exception at run time.</span></span>  
  
 <span data-ttu-id="e374c-109">이 옵션의 기본값은 **-checked-** 이며, 오버플로 검사는 해제되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e374c-109">The default value for this option is **-checked-**; overflow checking is disabled.</span></span>

 <span data-ttu-id="e374c-110">경우에 따라 대형 애플리케이션을 빌드하는 데 사용되는 자동화된 도구가 +로 -checked를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e374c-110">Sometimes, automated tools that are used to build large applications set -checked to +.</span></span> <span data-ttu-id="e374c-111">-checked-를 사용하는 하나의 시나리오는 -checked-를 지정하여 도구의 글로벌 기본값을 재정의하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e374c-111">One scenario for using -checked- is to override the tool's global default by specifying -checked-.</span></span>

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="e374c-112">Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="e374c-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="e374c-113">프로젝트 **속성** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e374c-113">Open the project's **Properties** page.</span></span> <span data-ttu-id="e374c-114">자세한 내용은 [프로젝트 디자이너, 빌드 페이지(C#)](/visualstudio/ide/reference/build-page-project-designer-csharp)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e374c-114">For more information, see [Build Page, Project Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span></span>  
  
2. <span data-ttu-id="e374c-115">**빌드** 속성 페이지를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e374c-115">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="e374c-116">**고급** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e374c-116">Click the **Advanced** button.</span></span>  
  
4. <span data-ttu-id="e374c-117">**산술 연산 오버플로 확인** 속성을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="e374c-117">Modify the **Check for arithmetic overflow** property.</span></span>  
  
 <span data-ttu-id="e374c-118">프로그래밍 방식으로 이 컴파일러 옵션에 액세스하려면 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.CheckForOverflowUnderflow%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e374c-118">To access this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.CheckForOverflowUnderflow%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e374c-119">예제</span><span class="sxs-lookup"><span data-stu-id="e374c-119">Example</span></span>  
 <span data-ttu-id="e374c-120">다음 명령은 `t2.cs`를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="e374c-120">The following command compiles `t2.cs`.</span></span> <span data-ttu-id="e374c-121">명령에서 `-checked`를 사용하면 `checked` 또는 `unchecked` 키워드의 범위에 없고 데이터 형식 범위를 벗어난 값을 생성하는 파일의 정수 산술 문이 런타임에 예외를 일으키도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e374c-121">The use of `-checked` in the command specifies that any integer arithmetic statement in the file that is not in the scope of a `checked` or `unchecked` keyword, and that results in a value that is outside the range of the data type, causes an exception at run time.</span></span>  
  
```console  
csc t2.cs -checked  
```  
  
## <a name="see-also"></a><span data-ttu-id="e374c-122">참조</span><span class="sxs-lookup"><span data-stu-id="e374c-122">See also</span></span>

- [<span data-ttu-id="e374c-123">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="e374c-123">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="e374c-124">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="e374c-124">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
