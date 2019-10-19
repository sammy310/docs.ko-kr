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
ms.openlocfilehash: 469e22aef9d746fc55e04ba884d17d60d8baa85a
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583084"
---
# <a name="-optionstrict"></a><span data-ttu-id="31b22-102">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="31b22-102">-optionstrict</span></span>

<span data-ttu-id="31b22-103">엄격한 형식 의미 체계를 적용 하 여 암시적 형식 변환을 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="31b22-103">Enforces strict type semantics to restrict implicit type conversions.</span></span>

## <a name="syntax"></a><span data-ttu-id="31b22-104">구문</span><span class="sxs-lookup"><span data-stu-id="31b22-104">Syntax</span></span>

```console
-optionstrict[+ | -]
-optionstrict[:custom]
```

## <a name="arguments"></a><span data-ttu-id="31b22-105">인수</span><span class="sxs-lookup"><span data-stu-id="31b22-105">Arguments</span></span>

<span data-ttu-id="31b22-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="31b22-106">`+` &#124; `-`</span></span>  
<span data-ttu-id="31b22-107">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="31b22-107">Optional.</span></span> <span data-ttu-id="31b22-108">@No__t_0 옵션은 암시적 형식 변환을 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="31b22-108">The `-optionstrict+` option restricts implicit type conversion.</span></span> <span data-ttu-id="31b22-109">이 옵션의 기본값은 `-optionstrict-`입니다.</span><span class="sxs-lookup"><span data-stu-id="31b22-109">The default for this option is `-optionstrict-`.</span></span> <span data-ttu-id="31b22-110">@No__t_0 옵션은 `-optionstrict`와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="31b22-110">The `-optionstrict+` option is the same as `-optionstrict`.</span></span> <span data-ttu-id="31b22-111">관대 한 형식 의미 체계에 대해 둘 다 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31b22-111">You can use both for permissive type semantics.</span></span>

`custom`  
<span data-ttu-id="31b22-112">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="31b22-112">Required.</span></span> <span data-ttu-id="31b22-113">엄격한 언어 의미 체계를 준수 하지 않을 때 경고 합니다.</span><span class="sxs-lookup"><span data-stu-id="31b22-113">Warn when strict language semantics are not respected.</span></span>

## <a name="remarks"></a><span data-ttu-id="31b22-114">주의</span><span class="sxs-lookup"><span data-stu-id="31b22-114">Remarks</span></span>

<span data-ttu-id="31b22-115">@No__t_0 적용 되는 경우에는 확장 형식 변환만 암시적으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31b22-115">When `-optionstrict+` is in effect, only widening type conversions can be made implicitly.</span></span> <span data-ttu-id="31b22-116">정수 형식 개체에 `Decimal` 형식 개체를 할당 하는 등의 암시적 축소 형식 변환은 오류로 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="31b22-116">Implicit narrowing type conversions, such as assigning a `Decimal` type object to an integer type object, are reported as errors.</span></span>

<span data-ttu-id="31b22-117">암시적 축소 형식 변환에 대 한 경고를 생성 하려면 `-optionstrict:custom`을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="31b22-117">To generate warnings for implicit narrowing type conversions, use `-optionstrict:custom`.</span></span> <span data-ttu-id="31b22-118">@No__t_0를 사용 하 여 특정 경고를 무시 하 고 `-warnaserror:numberlist` 특정 경고를 오류로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="31b22-118">Use `-nowarn:numberlist` to ignore particular warnings and `-warnaserror:numberlist` to treat particular warnings as errors.</span></span>

### <a name="to-set--optionstrict-in-the-visual-studio-ide"></a><span data-ttu-id="31b22-119">Visual Studio IDE에서-option strict를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="31b22-119">To set -optionstrict in the Visual Studio IDE</span></span>

1. <span data-ttu-id="31b22-120">**솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="31b22-120">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="31b22-121">**프로젝트** 메뉴에서 속성을 클릭 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="31b22-121">On the **Project** menu, click **Properties.**</span></span>

2. <span data-ttu-id="31b22-122">**컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="31b22-122">Click the **Compile** tab.</span></span>

3. <span data-ttu-id="31b22-123">**Option Strict** 상자에서 값을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="31b22-123">Modify the value in the **Option Strict** box.</span></span>

### <a name="to-set--optionstrict-programmatically"></a><span data-ttu-id="31b22-124">프로그래밍 방식으로-option strict 설정</span><span class="sxs-lookup"><span data-stu-id="31b22-124">To set -optionstrict programmatically</span></span>

<span data-ttu-id="31b22-125">[Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="31b22-125">See [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>

## <a name="example"></a><span data-ttu-id="31b22-126">예제</span><span class="sxs-lookup"><span data-stu-id="31b22-126">Example</span></span>

<span data-ttu-id="31b22-127">다음 코드는 엄격한 형식 의미 체계를 사용 하 여 `Test.vb`을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="31b22-127">The following code compiles `Test.vb` using strict type semantics.</span></span>

```console
vbc -optionstrict+ test.vb
```

## <a name="see-also"></a><span data-ttu-id="31b22-128">참조</span><span class="sxs-lookup"><span data-stu-id="31b22-128">See also</span></span>

- [<span data-ttu-id="31b22-129">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="31b22-129">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="31b22-130">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="31b22-130">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="31b22-131">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="31b22-131">-optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="31b22-132">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="31b22-132">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="31b22-133">-nowarn</span><span class="sxs-lookup"><span data-stu-id="31b22-133">-nowarn</span></span>](../../../visual-basic/reference/command-line-compiler/nowarn.md)
- [<span data-ttu-id="31b22-134">-warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="31b22-134">-warnaserror (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/warnaserror.md)
- [<span data-ttu-id="31b22-135">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="31b22-135">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="31b22-136">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="31b22-136">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="31b22-137">옵션 대화 상자, 프로젝트, Visual Basic 기본값</span><span class="sxs-lookup"><span data-stu-id="31b22-137">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
