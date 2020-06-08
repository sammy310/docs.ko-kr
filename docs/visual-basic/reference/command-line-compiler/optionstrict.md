---
title: -optionstrict
ms.date: 07/20/2015
f1_keywords:
- -optionstrict
helpviewer_keywords:
- -optionstrict compiler option [Visual Basic]
- optionstrict compiler option [Visual Basic]
- /optionstrict compiler option [Visual Basic]
ms.assetid: c7b10086-0fa4-49db-b3c8-4ae0db5957da
ms.openlocfilehash: 3dd12971a082869c32b6292ed45e2014b8b0e2c0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400541"
---
# <a name="-optionstrict"></a><span data-ttu-id="bf2af-102">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="bf2af-102">-optionstrict</span></span>

<span data-ttu-id="bf2af-103">엄격한 형식 의미 체계를 적용하여 암시적 형식 변환을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="bf2af-103">Enforces strict type semantics to restrict implicit type conversions.</span></span>

## <a name="syntax"></a><span data-ttu-id="bf2af-104">구문</span><span class="sxs-lookup"><span data-stu-id="bf2af-104">Syntax</span></span>

```console
-optionstrict[+ | -]
-optionstrict[:custom]
```

## <a name="arguments"></a><span data-ttu-id="bf2af-105">인수</span><span class="sxs-lookup"><span data-stu-id="bf2af-105">Arguments</span></span>

<span data-ttu-id="bf2af-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="bf2af-106">`+` &#124; `-`</span></span>  
<span data-ttu-id="bf2af-107">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bf2af-107">Optional.</span></span> <span data-ttu-id="bf2af-108">`-optionstrict+` 옵션은 암시적 형식 변환을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="bf2af-108">The `-optionstrict+` option restricts implicit type conversion.</span></span> <span data-ttu-id="bf2af-109">이 옵션의 기본값은 `-optionstrict-`입니다.</span><span class="sxs-lookup"><span data-stu-id="bf2af-109">The default for this option is `-optionstrict-`.</span></span> <span data-ttu-id="bf2af-110">`-optionstrict+` 옵션은 `-optionstrict`와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="bf2af-110">The `-optionstrict+` option is the same as `-optionstrict`.</span></span> <span data-ttu-id="bf2af-111">허용 형식 의미 체계에 둘 다 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf2af-111">You can use both for permissive type semantics.</span></span>

`custom`  
<span data-ttu-id="bf2af-112">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="bf2af-112">Required.</span></span> <span data-ttu-id="bf2af-113">엄격한 언어 의미 체계를 준수하지 않을 경우 경고합니다.</span><span class="sxs-lookup"><span data-stu-id="bf2af-113">Warn when strict language semantics are not respected.</span></span>

## <a name="remarks"></a><span data-ttu-id="bf2af-114">설명</span><span class="sxs-lookup"><span data-stu-id="bf2af-114">Remarks</span></span>

<span data-ttu-id="bf2af-115">`-optionstrict+`가 적용되면 확장 형식 변환만 암시적으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf2af-115">When `-optionstrict+` is in effect, only widening type conversions can be made implicitly.</span></span> <span data-ttu-id="bf2af-116">정수 형식 개체에 `Decimal` 형식 개체를 할당하는 등의 암시적 축소 형식 변환은 오류로 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf2af-116">Implicit narrowing type conversions, such as assigning a `Decimal` type object to an integer type object, are reported as errors.</span></span>

<span data-ttu-id="bf2af-117">암시적 축소 형식 변환에 대한 경고를 생성하려면 `-optionstrict:custom`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bf2af-117">To generate warnings for implicit narrowing type conversions, use `-optionstrict:custom`.</span></span> <span data-ttu-id="bf2af-118">`-nowarn:numberlist`를 사용하여 특정 경고를 무시하고, `-warnaserror:numberlist`를 사용하여 특정 경고를 오류로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="bf2af-118">Use `-nowarn:numberlist` to ignore particular warnings and `-warnaserror:numberlist` to treat particular warnings as errors.</span></span>

### <a name="to-set--optionstrict-in-the-visual-studio-ide"></a><span data-ttu-id="bf2af-119">Visual Studio IDE에서 -optionstrict를 설정하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="bf2af-119">To set -optionstrict in the Visual Studio IDE</span></span>

1. <span data-ttu-id="bf2af-120">**솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf2af-120">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="bf2af-121">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bf2af-121">On the **Project** menu, click **Properties.**</span></span>

2. <span data-ttu-id="bf2af-122">**컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bf2af-122">Click the **Compile** tab.</span></span>

3. <span data-ttu-id="bf2af-123">**Option Strict** 상자에서 값을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="bf2af-123">Modify the value in the **Option Strict** box.</span></span>

### <a name="to-set--optionstrict-programmatically"></a><span data-ttu-id="bf2af-124">프로그래밍 방식으로 -optionstrict를 설정하려면</span><span class="sxs-lookup"><span data-stu-id="bf2af-124">To set -optionstrict programmatically</span></span>

<span data-ttu-id="bf2af-125">[Option Strict 문](../../language-reference/statements/option-strict-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bf2af-125">See [Option Strict Statement](../../language-reference/statements/option-strict-statement.md).</span></span>

## <a name="example"></a><span data-ttu-id="bf2af-126">예제</span><span class="sxs-lookup"><span data-stu-id="bf2af-126">Example</span></span>

<span data-ttu-id="bf2af-127">다음 코드에서는 엄격한 형식 의미 체계를 사용하여 `Test.vb`를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="bf2af-127">The following code compiles `Test.vb` using strict type semantics.</span></span>

```console
vbc -optionstrict+ test.vb
```

## <a name="see-also"></a><span data-ttu-id="bf2af-128">참조</span><span class="sxs-lookup"><span data-stu-id="bf2af-128">See also</span></span>

- [<span data-ttu-id="bf2af-129">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="bf2af-129">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="bf2af-130">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="bf2af-130">-optioncompare</span></span>](optioncompare.md)
- [<span data-ttu-id="bf2af-131">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="bf2af-131">-optionexplicit</span></span>](optionexplicit.md)
- [<span data-ttu-id="bf2af-132">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="bf2af-132">-optioninfer</span></span>](optioninfer.md)
- [<span data-ttu-id="bf2af-133">-nowarn</span><span class="sxs-lookup"><span data-stu-id="bf2af-133">-nowarn</span></span>](nowarn.md)
- [<span data-ttu-id="bf2af-134">-warnaserror(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf2af-134">-warnaserror (Visual Basic)</span></span>](warnaserror.md)
- [<span data-ttu-id="bf2af-135">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="bf2af-135">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="bf2af-136">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="bf2af-136">Option Strict Statement</span></span>](../../language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="bf2af-137">옵션 대화 상자, 프로젝트, Visual Basic 기본값</span><span class="sxs-lookup"><span data-stu-id="bf2af-137">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
