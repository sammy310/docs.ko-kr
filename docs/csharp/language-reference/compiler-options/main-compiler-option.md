---
description: -main(C# 컴파일러 옵션)
title: -main(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /main
helpviewer_keywords:
- -main compiler option [C#]
- main compiler option [C#]
- /main compiler option [C#]
ms.assetid: 975cf4d5-36ac-4530-826c-4aad0c7f2049
ms.openlocfilehash: c27898de2a7cc2f3c01c51f8de1122e81b2233b4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194117"
---
# <a name="-main-c-compiler-options"></a><span data-ttu-id="51b66-103">-main(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="51b66-103">-main (C# Compiler Options)</span></span>

<span data-ttu-id="51b66-104">이 옵션은 둘 이상의 클래스에 **Main** 메서드가 포함된 경우 프로그램에 대한 진입점을 포함하는 클래스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="51b66-104">This option specifies the class that contains the entry point to the program, if more than one class contains a **Main** method.</span></span>

## <a name="syntax"></a><span data-ttu-id="51b66-105">구문</span><span class="sxs-lookup"><span data-stu-id="51b66-105">Syntax</span></span>

```console
-main:class
```

## <a name="arguments"></a><span data-ttu-id="51b66-106">인수</span><span class="sxs-lookup"><span data-stu-id="51b66-106">Arguments</span></span>

 `class`  
 <span data-ttu-id="51b66-107">**Main** 메서드를 포함하는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="51b66-107">The type that contains the **Main** method.</span></span>  
 <span data-ttu-id="51b66-108">제공된 클래스 이름은 완전히 정규화되어야 하며, 클래스를 포함하는 전체 네임스페이스와 클래스 이름을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51b66-108">The provided class name must be fully qualified; it must include the full namespace containing the class, followed by the class name.</span></span> <span data-ttu-id="51b66-109">예를 들어 `Main` 메서드가 `MyApplication.Core` 네임스페이스의 `Program` 클래스 내에 있는 경우 컴파일러 옵션은 `-main:MyApplication.Core.Program`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51b66-109">For example, when the `Main` method is located inside the `Program` class in the `MyApplication.Core` namespace, the compiler option has to be `-main:MyApplication.Core.Program`.</span></span>

## <a name="remarks"></a><span data-ttu-id="51b66-110">설명</span><span class="sxs-lookup"><span data-stu-id="51b66-110">Remarks</span></span>

<span data-ttu-id="51b66-111">컴파일에 [Main](../../programming-guide/main-and-command-args/index.md) 메서드가 있는 형식이 둘 이상 포함된 경우 프로그램에 대한 진입점으로 사용할 **Main** 메서드를 포함하는 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51b66-111">If your compilation includes more than one type with a [Main](../../programming-guide/main-and-command-args/index.md) method, you can specify which type contains the **Main** method that you want to use as the entry point into the program.</span></span>

<span data-ttu-id="51b66-112">이 옵션은 *.exe* 파일을 컴파일할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="51b66-112">This option is for use when compiling an *.exe* file.</span></span>

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="51b66-113">Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="51b66-113">To set this compiler option in the Visual Studio development environment</span></span>

1. <span data-ttu-id="51b66-114">프로젝트 **속성** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="51b66-114">Open the project's **Properties** page.</span></span>

2. <span data-ttu-id="51b66-115">**애플리케이션** 속성 페이지를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="51b66-115">Click the **Application** property page.</span></span>

3. <span data-ttu-id="51b66-116">**시작 개체** 속성을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="51b66-116">Modify the **Startup object** property.</span></span>

    <span data-ttu-id="51b66-117">프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면 <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="51b66-117">To set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.</span></span>

### <a name="to-set-this-compiler-option-by-manually-editing-the-csproj-file"></a><span data-ttu-id="51b66-118">수동으로 *.csproj* 파일을 편집하여 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="51b66-118">To set this compiler option by manually editing the *.csproj* file</span></span>

<span data-ttu-id="51b66-119">.csproj 파일을 편집하고 `PropertyGroup` 섹션 내에 `StartupObject` 요소를 추가하여 이 옵션을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51b66-119">You can set this option by editing the .csproj file and adding an element `StartupObject` inside the `PropertyGroup` section.</span></span> <span data-ttu-id="51b66-120">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="51b66-120">For example:</span></span>

```xml
  <PropertyGroup>
    ...
    <StartupObject>MyApplication.Core.Program</StartupObject>
  </PropertyGroup>
```

## <a name="example"></a><span data-ttu-id="51b66-121">예제</span><span class="sxs-lookup"><span data-stu-id="51b66-121">Example</span></span>

<span data-ttu-id="51b66-122">**Main** 메서드가 `Test2`에 있다고 지정하여 `t2.cs` 및 `t3.cs`를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="51b66-122">Compile `t2.cs` and `t3.cs`, specifying that the **Main** method will be found in `Test2`:</span></span>

```console
csc t2.cs t3.cs -main:Test2
```

## <a name="see-also"></a><span data-ttu-id="51b66-123">참조</span><span class="sxs-lookup"><span data-stu-id="51b66-123">See also</span></span>

- [<span data-ttu-id="51b66-124">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="51b66-124">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="51b66-125">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="51b66-125">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
