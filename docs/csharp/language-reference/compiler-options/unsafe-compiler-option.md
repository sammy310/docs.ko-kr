---
description: -unsafe(C# 컴파일러 옵션)
title: -unsafe(C# 컴파일러 옵션)
ms.date: 04/25/2018
f1_keywords:
- /unsafe
helpviewer_keywords:
- -unsafe compiler option [C#]
- unsafe compiler option [C#]
- /unsafe compiler option [C#]
ms.openlocfilehash: 0f6d94dd25a020d96430746c4b5e7aefd0f679da
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89140843"
---
# <a name="-unsafe-c-compiler-options"></a><span data-ttu-id="cb2bd-103">-unsafe(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="cb2bd-103">-unsafe (C# Compiler Options)</span></span>

<span data-ttu-id="cb2bd-104">**-unsafe** 컴파일러 옵션을 사용하면 [unsafe](../keywords/unsafe.md) 키워드를 사용하는 코드를 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb2bd-104">The **-unsafe** compiler option allows code that uses the [unsafe](../keywords/unsafe.md) keyword to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb2bd-105">구문</span><span class="sxs-lookup"><span data-stu-id="cb2bd-105">Syntax</span></span>  
  
```console  
-unsafe  
```  
  
## <a name="remarks"></a><span data-ttu-id="cb2bd-106">설명</span><span class="sxs-lookup"><span data-stu-id="cb2bd-106">Remarks</span></span>

<span data-ttu-id="cb2bd-107">안전하지 않은 코드에 대한 자세한 내용은 [안전하지 않은 코드 및 포인터](../../programming-guide/unsafe-code-pointers/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cb2bd-107">For more information about unsafe code, see [Unsafe Code and Pointers](../../programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="cb2bd-108">Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="cb2bd-108">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="cb2bd-109">프로젝트 **속성** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="cb2bd-109">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="cb2bd-110">**빌드** 속성 페이지를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cb2bd-110">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="cb2bd-111">**안전하지 않은 코드 허용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cb2bd-111">Select the **Allow Unsafe Code** check box.</span></span>  
  
### <a name="to-add-this-option-in-a-csproj-file"></a><span data-ttu-id="cb2bd-112">이 옵션을 csproj 파일에 추가하려면</span><span class="sxs-lookup"><span data-stu-id="cb2bd-112">To add this option in a csproj file</span></span>

<span data-ttu-id="cb2bd-113">프로젝트에 대한 .csproj 파일을 열고 다음 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cb2bd-113">Open the .csproj file for a project, and add the following elements:</span></span>

```xml
  <PropertyGroup>
    <AllowUnsafeBlocks>true</AllowUnsafeBlocks>
  </PropertyGroup>
```

 <span data-ttu-id="cb2bd-114">이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cb2bd-114">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb2bd-115">예제</span><span class="sxs-lookup"><span data-stu-id="cb2bd-115">Example</span></span>

<span data-ttu-id="cb2bd-116">안전하지 않은 모드에 대해 `in.cs` 컴파일:</span><span class="sxs-lookup"><span data-stu-id="cb2bd-116">Compile `in.cs` for unsafe mode:</span></span>  
  
```console  
csc -unsafe in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="cb2bd-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cb2bd-117">See also</span></span>

- [<span data-ttu-id="cb2bd-118">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="cb2bd-118">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="cb2bd-119">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="cb2bd-119">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
