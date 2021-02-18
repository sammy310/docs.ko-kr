---
description: '자세한 정보: -optionstrict'
title: -optionstrict
ms.date: 07/20/2015
f1_keywords:
- -optionstrict
helpviewer_keywords:
- -optionstrict compiler option [Visual Basic]
- optionstrict compiler option [Visual Basic]
- /optionstrict compiler option [Visual Basic]
ms.assetid: c7b10086-0fa4-49db-b3c8-4ae0db5957da
ms.openlocfilehash: ad58c7775eaa77c1bf693629cf12cc70e4222920
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100475905"
---
# <a name="-optionstrict"></a><span data-ttu-id="f4f1a-103">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="f4f1a-103">-optionstrict</span></span>

<span data-ttu-id="f4f1a-104">엄격한 형식 의미 체계를 적용하여 암시적 형식 변환을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="f4f1a-104">Enforces strict type semantics to restrict implicit type conversions.</span></span>

## <a name="syntax"></a><span data-ttu-id="f4f1a-105">구문</span><span class="sxs-lookup"><span data-stu-id="f4f1a-105">Syntax</span></span>

```console
-optionstrict[+ | -]
-optionstrict[:custom]
```

## <a name="arguments"></a><span data-ttu-id="f4f1a-106">인수</span><span class="sxs-lookup"><span data-stu-id="f4f1a-106">Arguments</span></span>

<span data-ttu-id="f4f1a-107">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="f4f1a-107">`+` &#124; `-`</span></span>  
<span data-ttu-id="f4f1a-108">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="f4f1a-108">Optional.</span></span> <span data-ttu-id="f4f1a-109">`-optionstrict+` 옵션은 암시적 형식 변환을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="f4f1a-109">The `-optionstrict+` option restricts implicit type conversion.</span></span> <span data-ttu-id="f4f1a-110">이 옵션의 기본값은 `-optionstrict-`입니다.</span><span class="sxs-lookup"><span data-stu-id="f4f1a-110">The default for this option is `-optionstrict-`.</span></span> <span data-ttu-id="f4f1a-111">`-optionstrict+` 옵션은 `-optionstrict`와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="f4f1a-111">The `-optionstrict+` option is the same as `-optionstrict`.</span></span> <span data-ttu-id="f4f1a-112">허용 형식 의미 체계에 둘 다 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4f1a-112">You can use both for permissive type semantics.</span></span>

`custom`  
<span data-ttu-id="f4f1a-113">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="f4f1a-113">Required.</span></span> <span data-ttu-id="f4f1a-114">엄격한 언어 의미 체계를 준수하지 않을 경우 경고합니다.</span><span class="sxs-lookup"><span data-stu-id="f4f1a-114">Warn when strict language semantics are not respected.</span></span>

## <a name="remarks"></a><span data-ttu-id="f4f1a-115">설명</span><span class="sxs-lookup"><span data-stu-id="f4f1a-115">Remarks</span></span>

<span data-ttu-id="f4f1a-116">`-optionstrict+`가 적용되면 확장 형식 변환만 암시적으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4f1a-116">When `-optionstrict+` is in effect, only widening type conversions can be made implicitly.</span></span> <span data-ttu-id="f4f1a-117">정수 형식 개체에 `Decimal` 형식 개체를 할당하는 등의 암시적 축소 형식 변환은 오류로 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4f1a-117">Implicit narrowing type conversions, such as assigning a `Decimal` type object to an integer type object, are reported as errors.</span></span>

<span data-ttu-id="f4f1a-118">암시적 축소 형식 변환에 대한 경고를 생성하려면 `-optionstrict:custom`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f4f1a-118">To generate warnings for implicit narrowing type conversions, use `-optionstrict:custom`.</span></span> <span data-ttu-id="f4f1a-119">`-nowarn:numberlist`를 사용하여 특정 경고를 무시하고, `-warnaserror:numberlist`를 사용하여 특정 경고를 오류로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="f4f1a-119">Use `-nowarn:numberlist` to ignore particular warnings and `-warnaserror:numberlist` to treat particular warnings as errors.</span></span>

### <a name="to-set--optionstrict-in-the-visual-studio-ide"></a><span data-ttu-id="f4f1a-120">Visual Studio IDE에서 -optionstrict를 설정하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f4f1a-120">To set -optionstrict in the Visual Studio IDE</span></span>

1. <span data-ttu-id="f4f1a-121">**솔루션 탐색기** 에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f4f1a-121">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="f4f1a-122">**프로젝트** 메뉴에서 **속성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f4f1a-122">On the **Project** menu, click **Properties.**</span></span>

2. <span data-ttu-id="f4f1a-123">**컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f4f1a-123">Click the **Compile** tab.</span></span>

3. <span data-ttu-id="f4f1a-124">**Option Strict** 상자에서 값을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="f4f1a-124">Modify the value in the **Option Strict** box.</span></span>

### <a name="to-set--optionstrict-programmatically"></a><span data-ttu-id="f4f1a-125">프로그래밍 방식으로 -optionstrict를 설정하려면</span><span class="sxs-lookup"><span data-stu-id="f4f1a-125">To set -optionstrict programmatically</span></span>

<span data-ttu-id="f4f1a-126">[Option Strict 문](../../language-reference/statements/option-strict-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f4f1a-126">See [Option Strict Statement](../../language-reference/statements/option-strict-statement.md).</span></span>

## <a name="example"></a><span data-ttu-id="f4f1a-127">예제</span><span class="sxs-lookup"><span data-stu-id="f4f1a-127">Example</span></span>

<span data-ttu-id="f4f1a-128">다음 코드에서는 엄격한 형식 의미 체계를 사용하여 `Test.vb`를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="f4f1a-128">The following code compiles `Test.vb` using strict type semantics.</span></span>

```console
vbc -optionstrict+ test.vb
```

## <a name="see-also"></a><span data-ttu-id="f4f1a-129">참조</span><span class="sxs-lookup"><span data-stu-id="f4f1a-129">See also</span></span>

- [<span data-ttu-id="f4f1a-130">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="f4f1a-130">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="f4f1a-131">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="f4f1a-131">-optioncompare</span></span>](optioncompare.md)
- [<span data-ttu-id="f4f1a-132">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="f4f1a-132">-optionexplicit</span></span>](optionexplicit.md)
- [<span data-ttu-id="f4f1a-133">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="f4f1a-133">-optioninfer</span></span>](optioninfer.md)
- [<span data-ttu-id="f4f1a-134">-nowarn</span><span class="sxs-lookup"><span data-stu-id="f4f1a-134">-nowarn</span></span>](nowarn.md)
- [<span data-ttu-id="f4f1a-135">-warnaserror(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f4f1a-135">-warnaserror (Visual Basic)</span></span>](warnaserror.md)
- [<span data-ttu-id="f4f1a-136">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="f4f1a-136">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="f4f1a-137">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="f4f1a-137">Option Strict Statement</span></span>](../../language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="f4f1a-138">옵션 대화 상자, 프로젝트, Visual Basic 기본값</span><span class="sxs-lookup"><span data-stu-id="f4f1a-138">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
