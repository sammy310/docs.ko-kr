---
description: -warn(C# 컴파일러 옵션)
title: -warn(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /warn
helpviewer_keywords:
- warning level [C#]
- /w compiler option [C#]
- -w compiler option [C#]
- -warn compiler option [C#]
- /warn compiler option [C#]
- w compiler option [C#]
- warn compiler option [C#]
ms.custom: updateeachrelease
ms.assetid: 5f80ff59-4991-4382-9f9a-77da18446e71
ms.openlocfilehash: d59274423e6f9844d3ab22f3ac513ba1a05d7f07
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91171353"
---
# <a name="-warn-c-compiler-options"></a><span data-ttu-id="2b9af-103">-warn(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="2b9af-103">-warn (C# Compiler Options)</span></span>

<span data-ttu-id="2b9af-104">**-warn** 옵션은 컴파일러에서 표시할 경고 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9af-104">The **-warn** option specifies the warning level for the compiler to display.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b9af-105">구문</span><span class="sxs-lookup"><span data-stu-id="2b9af-105">Syntax</span></span>  
  
```console  
-warn:option  
```  
  
## <a name="arguments"></a><span data-ttu-id="2b9af-106">인수</span><span class="sxs-lookup"><span data-stu-id="2b9af-106">Arguments</span></span>  

 `option`  
 <span data-ttu-id="2b9af-107">컴파일에 대해 표시할 경고 수준입니다. 숫자가 낮으면 높은 심각도 경고만 표시되고, 숫자가 높으면 더 많은 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b9af-107">The warning level you want displayed for the compilation: Lower numbers show only high severity warnings; higher numbers show more warnings.</span></span> <span data-ttu-id="2b9af-108">값은 0 또는 양의 정수여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9af-108">The value must be zero or a positive integer:</span></span>

|<span data-ttu-id="2b9af-109">경고 수준</span><span class="sxs-lookup"><span data-stu-id="2b9af-109">Warning level</span></span>|<span data-ttu-id="2b9af-110">의미</span><span class="sxs-lookup"><span data-stu-id="2b9af-110">Meaning</span></span>|
|-------------------|-------------|
|<span data-ttu-id="2b9af-111">0</span><span class="sxs-lookup"><span data-stu-id="2b9af-111">0</span></span>|<span data-ttu-id="2b9af-112">모든 경고 메시지 내보내기를 끕니다.</span><span class="sxs-lookup"><span data-stu-id="2b9af-112">Turns off emission of all warning messages.</span></span>|
|<span data-ttu-id="2b9af-113">1</span><span class="sxs-lookup"><span data-stu-id="2b9af-113">1</span></span>|<span data-ttu-id="2b9af-114">심각한 경고 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9af-114">Displays severe warning messages.</span></span>|  
|<span data-ttu-id="2b9af-115">2</span><span class="sxs-lookup"><span data-stu-id="2b9af-115">2</span></span>|<span data-ttu-id="2b9af-116">수준 1 경고와 덜 심각한 특정 경고(예: 클래스 멤버 숨기기에 대한 경고)를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9af-116">Displays level 1 warnings plus certain, less-severe warnings, such as warnings about hiding class members.</span></span>|  
|<span data-ttu-id="2b9af-117">3</span><span class="sxs-lookup"><span data-stu-id="2b9af-117">3</span></span>|<span data-ttu-id="2b9af-118">수준 2 경고와 덜 심각한 특정 경고(예: 항상 `true` 또는 `false`로 평가되는 식에 대한 경고)를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9af-118">Displays level 2 warnings plus certain, less-severe warnings, such as warnings about expressions that always evaluate to `true` or `false`.</span></span>|  
|<span data-ttu-id="2b9af-119">4(기본값)</span><span class="sxs-lookup"><span data-stu-id="2b9af-119">4 (the default)</span></span>|<span data-ttu-id="2b9af-120">모든 수준 3 경고와 정보 경고를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9af-120">Displays all level 3 warnings plus informational warnings.</span></span>|
|<span data-ttu-id="2b9af-121">5</span><span class="sxs-lookup"><span data-stu-id="2b9af-121">5</span></span>|<span data-ttu-id="2b9af-122">수준 4 경고와 함께 C# 9.0에 제공된 컴파일러의 [추가 경고](https://github.com/dotnet/roslyn/blob/a6013f3213c902c0973b2d371c3007217d610533/docs/compilers/CSharp/Warnversion%20Warning%20Waves.md)를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9af-122">Displays level 4 warnings plus [additional warnings](https://github.com/dotnet/roslyn/blob/a6013f3213c902c0973b2d371c3007217d610533/docs/compilers/CSharp/Warnversion%20Warning%20Waves.md) from the compiler shipped with C# 9.0.</span></span>|
|<span data-ttu-id="2b9af-123">5보다 큼</span><span class="sxs-lookup"><span data-stu-id="2b9af-123">Greater than 5</span></span>|<span data-ttu-id="2b9af-124">5보다 큰 값은 5로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b9af-124">Any value greater than 5 will be treated as 5.</span></span> <span data-ttu-id="2b9af-125">일반적으로 큰 임의 값(예: `9999`)을 배치하여 컴파일러가 새 경고 수준으로 업데이트되는 경우 항상 모든 경고가 표시되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9af-125">You generally put arbitrary large value (for example, `9999`) to make sure you always have all warnings if the compiler is updated with new warning levels.</span></span>|
  
## <a name="remarks"></a><span data-ttu-id="2b9af-126">설명</span><span class="sxs-lookup"><span data-stu-id="2b9af-126">Remarks</span></span>  

 <span data-ttu-id="2b9af-127">오류 또는 경고에 대한 정보를 가져오려면 도움말 색인에서 오류 코드를 조회할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b9af-127">To get information about an error or warning, you can look up the error code in the Help Index.</span></span> <span data-ttu-id="2b9af-128">오류 또는 경고에 대한 정보를 가져오는 다른 방법은 [C# 컴파일러 오류](../compiler-messages/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2b9af-128">For other ways to get information about an error or warning, see [C# Compiler Errors](../compiler-messages/index.md).</span></span>  
  
 <span data-ttu-id="2b9af-129">모든 경고를 오류로 처리하려면 [-warnaserror](./warnaserror-compiler-option.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9af-129">Use [-warnaserror](./warnaserror-compiler-option.md) to treat all warnings as errors.</span></span> <span data-ttu-id="2b9af-130">특정 경고를 사용하지 않으려면 [-nowarn](./nowarn-compiler-option.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9af-130">Use [-nowarn](./nowarn-compiler-option.md) to disable certain warnings.</span></span>  
  
 <span data-ttu-id="2b9af-131">**-w**는 **-warn**의 약식 형태입니다.</span><span class="sxs-lookup"><span data-stu-id="2b9af-131">**-w** is the short form of **-warn**.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="2b9af-132">Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="2b9af-132">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="2b9af-133">프로젝트 **속성** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2b9af-133">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="2b9af-134">**빌드** 속성 페이지를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9af-134">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="2b9af-135">**경고 수준** 속성을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9af-135">Modify the **Warning Level** property.</span></span>  
  
 <span data-ttu-id="2b9af-136">이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2b9af-136">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b9af-137">예제</span><span class="sxs-lookup"><span data-stu-id="2b9af-137">Example</span></span>  

 <span data-ttu-id="2b9af-138">`in.cs`를 컴파일하고 컴파일러에서 수준 1 경고만 표시하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9af-138">Compile `in.cs` and have the compiler only display level 1 warnings:</span></span>  
  
```console  
csc -warn:1 in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="2b9af-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2b9af-139">See also</span></span>

- [<span data-ttu-id="2b9af-140">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="2b9af-140">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="2b9af-141">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="2b9af-141">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
