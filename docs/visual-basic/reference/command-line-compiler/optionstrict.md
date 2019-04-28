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
ms.openlocfilehash: e18fe451ea4a80ac959ed61b66394920f8bf177f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788936"
---
# <a name="-optionstrict"></a><span data-ttu-id="fd499-102">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="fd499-102">-optionstrict</span></span>
<span data-ttu-id="fd499-103">암시적 형식 변환을 제한 하려면 엄격한 형식 의미 체계를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd499-103">Enforces strict type semantics to restrict implicit type conversions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd499-104">구문</span><span class="sxs-lookup"><span data-stu-id="fd499-104">Syntax</span></span>  
  
```  
-optionstrict[+ | -]  
-optionstrict[:custom]  
```  
  
## <a name="arguments"></a><span data-ttu-id="fd499-105">인수</span><span class="sxs-lookup"><span data-stu-id="fd499-105">Arguments</span></span>  
 <span data-ttu-id="fd499-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="fd499-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="fd499-107">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="fd499-107">Optional.</span></span> <span data-ttu-id="fd499-108">`-optionstrict+` 옵션으로 암시적 형식 변환을 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd499-108">The `-optionstrict+` option restricts implicit type conversion.</span></span> <span data-ttu-id="fd499-109">이 옵션의 기본값은 `-optionstrict-`합니다.</span><span class="sxs-lookup"><span data-stu-id="fd499-109">The default for this option is `-optionstrict-`.</span></span> <span data-ttu-id="fd499-110">합니다 `-optionstrict+` 옵션은 동일 `-optionstrict`합니다.</span><span class="sxs-lookup"><span data-stu-id="fd499-110">The `-optionstrict+` option is the same as `-optionstrict`.</span></span> <span data-ttu-id="fd499-111">관대 한 형식 의미 체계를 둘 다를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd499-111">You can use both for permissive type semantics.</span></span>  
  
 `custom`  
 <span data-ttu-id="fd499-112">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="fd499-112">Required.</span></span> <span data-ttu-id="fd499-113">엄격한 언어 의미 체계를 준수 하지 않을 경우 경고 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd499-113">Warn when strict language semantics are not respected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd499-114">설명</span><span class="sxs-lookup"><span data-stu-id="fd499-114">Remarks</span></span>  
 <span data-ttu-id="fd499-115">때 `-optionstrict+` 가 적용 된 경우 확장 형식 변환만 암시적으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd499-115">When `-optionstrict+` is in effect, only widening type conversions can be made implicitly.</span></span> <span data-ttu-id="fd499-116">암시적 축소 형식 변환, 할당 하는 등을 `Decimal` 입력 개체를 정수 형식 개체로, 오류로 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd499-116">Implicit narrowing type conversions, such as assigning a `Decimal` type object to an integer type object, are reported as errors.</span></span>  
  
 <span data-ttu-id="fd499-117">암시적 축소 형식 변환에 대 한 경고를 생성 하려면 사용 하 여 `-optionstrict:custom`입니다.</span><span class="sxs-lookup"><span data-stu-id="fd499-117">To generate warnings for implicit narrowing type conversions, use `-optionstrict:custom`.</span></span> <span data-ttu-id="fd499-118">사용 하 여 `-nowarn:numberlist` 특정 경고를 무시 하 고 `-warnaserror:numberlist` 특정 경고를 오류로 처리 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd499-118">Use `-nowarn:numberlist` to ignore particular warnings and `-warnaserror:numberlist` to treat particular warnings as errors.</span></span>  
  
### <a name="to-set--optionstrict-in-the-visual-studio-ide"></a><span data-ttu-id="fd499-119">-Optionstrict Visual Studio IDE에서 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="fd499-119">To set -optionstrict in the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="fd499-120">**솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fd499-120">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="fd499-121">에 **프로젝트** 메뉴에서 클릭 **속성입니다.**</span><span class="sxs-lookup"><span data-stu-id="fd499-121">On the **Project** menu, click **Properties.**</span></span>   
  
2. <span data-ttu-id="fd499-122">**컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fd499-122">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="fd499-123">값을 수정 합니다 **Option Strict** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="fd499-123">Modify the value in the **Option Strict** box.</span></span>  
  
### <a name="to-set--optionstrict-programmatically"></a><span data-ttu-id="fd499-124">-Optionstrict를 프로그래밍 방식으로 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="fd499-124">To set -optionstrict programmatically</span></span>  
  
- <span data-ttu-id="fd499-125">참조 [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fd499-125">See [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd499-126">예제</span><span class="sxs-lookup"><span data-stu-id="fd499-126">Example</span></span>  
 <span data-ttu-id="fd499-127">다음 코드에서는 `Test.vb` 엄격한 형식 의미 체계를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd499-127">The following code compiles `Test.vb` using strict type semantics.</span></span>  
  
```console
vbc -optionstrict+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="fd499-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="fd499-128">See also</span></span>

- [<span data-ttu-id="fd499-129">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="fd499-129">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="fd499-130">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="fd499-130">-optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="fd499-131">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="fd499-131">-optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="fd499-132">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="fd499-132">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="fd499-133">-nowarn</span><span class="sxs-lookup"><span data-stu-id="fd499-133">-nowarn</span></span>](../../../visual-basic/reference/command-line-compiler/nowarn.md)
- [<span data-ttu-id="fd499-134">-warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fd499-134">-warnaserror (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/warnaserror.md)
- [<span data-ttu-id="fd499-135">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="fd499-135">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="fd499-136">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="fd499-136">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="fd499-137">옵션 대화 상자, 프로젝트, Visual Basic 기본값</span><span class="sxs-lookup"><span data-stu-id="fd499-137">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
