---
description: '자세한 정보: 선언 된 요소 이름 (Visual Basic)'
title: Declared Element Names
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic], case sensitivity
- names [Visual Basic], Visual Basic rules
- naming conventions [Visual Basic]
- element names [Visual Basic]
- declared elements [Visual Basic], identifiers
- declarations [Visual Basic], elements
- declared elements [Visual Basic], valid names
- '[] escape characters [Visual Basic]'
- names [Visual Basic], elements
- declaration statements [Visual Basic], declared elements
- declaring elements [Visual Basic]
- identifiers [Visual Basic], declared elements
- case sensitivity, declared element names
- escape characters [Visual Basic]
- names [Visual Basic], declared elements
- declared elements [Visual Basic], about declared elements
- escaped names [Visual Basic]
- declared elements [Visual Basic], names
- names [Visual Basic], naming conventions
- identifiers [Visual Basic], elements
ms.assetid: 09d8843b-c0dc-4afe-9dab-87c439a69e66
ms.openlocfilehash: ba0a6d6b236c0c4e9ce81c37a1cca4e709cc5588
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100425687"
---
# <a name="declared-element-names-visual-basic"></a><span data-ttu-id="61c46-103">선언된 요소 이름(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="61c46-103">Declared Element Names (Visual Basic)</span></span>

<span data-ttu-id="61c46-104">선언 된 모든 요소에는 *식별자* 라고도 하는 이름이 있습니다 .이 이름은 코드에서이를 참조 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61c46-104">Every declared element has a name, also called an *identifier*, which is what the code uses to refer to it.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="61c46-105">규칙</span><span class="sxs-lookup"><span data-stu-id="61c46-105">Rules</span></span>  

 <span data-ttu-id="61c46-106">Visual Basic의 요소 이름은 다음 규칙을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c46-106">An element name in Visual Basic must observe the following rules:</span></span>  
  
- <span data-ttu-id="61c46-107">알파벳 문자 또는 밑줄 ()로 시작 해야 합니다 `_` .</span><span class="sxs-lookup"><span data-stu-id="61c46-107">It must begin with an alphabetic character or an underscore (`_`).</span></span>  
  
- <span data-ttu-id="61c46-108">영문자, 10 진수 및 밑줄만 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c46-108">It must only contain alphabetic characters, decimal digits, and underscores.</span></span>  
  
- <span data-ttu-id="61c46-109">밑줄로 시작 하는 경우 하나 이상의 알파벳 문자 또는 10 진수가 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c46-109">It must contain at least one alphabetic character or decimal digit if it begins with an underscore.</span></span>  
  
- <span data-ttu-id="61c46-110">길이는 1023 자이 하 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c46-110">It must not be more than 1023 characters long.</span></span>  
  
 <span data-ttu-id="61c46-111">1023 문자의 길이 제한은와 같이 정규화 된 이름의 전체 문자열에도 적용 됩니다 `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement` .</span><span class="sxs-lookup"><span data-stu-id="61c46-111">The length limit of 1023 characters also applies to the entire string of a fully qualified name, such as `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.</span></span>  
  
 <span data-ttu-id="61c46-112">다음 예제에서는 몇 가지 유효한 요소 이름을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="61c46-112">The following example shows some valid element names.</span></span>  
  
 `aB123__45`  
  
 `_567`  
  
 <span data-ttu-id="61c46-113">다음 예제에서는 일부 잘못 된 요소 이름을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="61c46-113">The following example shows some invalid element names.</span></span> <span data-ttu-id="61c46-114">첫 번째에는 밑줄만 포함 되 고, 두 번째는 10 진수로 시작 하 고, 세 번째에는 잘못 된 문자 ($)가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61c46-114">The first contains only an underscore, the second begins with a decimal digit, and the third contains an invalid character ($).</span></span>  
  
 `' Three INVALID element names`  
  
 `_`  
  
 `12ABC`  
  
 `xyz$wv`  
  
> [!CAUTION]
> <span data-ttu-id="61c46-115">밑줄 ()로 시작 하는 요소 이름은 `_` [언어 독립성 및 Language-Independent 구성 요소](../../../../standard/language-independence-and-language-independent-components.md) (cls)의 일부가 아니므로 cls 규격 코드는 이러한 이름을 정의 하는 구성 요소를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="61c46-115">Element names starting with an underscore (`_`) are not part of the [Language Independence and Language-Independent Components](../../../../standard/language-independence-and-language-independent-components.md) (CLS), so CLS-compliant code cannot use a component that defines such names.</span></span> <span data-ttu-id="61c46-116">그러나 요소 이름에서 다른 위치의 밑줄은 CLS 규격입니다.</span><span class="sxs-lookup"><span data-stu-id="61c46-116">However, an underscore in any other position in an element name is CLS-compliant.</span></span>  
  
### <a name="name-length-guidelines"></a><span data-ttu-id="61c46-117">이름 길이 지침</span><span class="sxs-lookup"><span data-stu-id="61c46-117">Name Length Guidelines</span></span>  

 <span data-ttu-id="61c46-118">실제로는 요소의 특성을 명확 하 게 식별 하는 동시에 이름을 최대한 짧게 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c46-118">As a practical matter, your name should be as short as possible while still clearly identifying the nature of the element.</span></span> <span data-ttu-id="61c46-119">이렇게 하면 코드의 가독성을 높이고 줄 길이와 소스 파일 크기를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="61c46-119">This improves the readability of your code and reduces line length and source-file size.</span></span>  
  
 <span data-ttu-id="61c46-120">반면에 요소는 요소가 나타내는 내용과 코드에서 사용 하는 방법을 적절 하 게 설명 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61c46-120">On the other hand, your name should not be so short that it does not adequately describe what the element represents and how your code uses it.</span></span> <span data-ttu-id="61c46-121">이는 코드의 가독성을 높이기 위해 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c46-121">This is important for the readability of your code.</span></span> <span data-ttu-id="61c46-122">다른 사용자가이를 이해 하려고 하거나 사용자가 작성 한 후 오랜 시간을 확인 하는 경우 적절 한 요소 이름을 통해 상당한 시간을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61c46-122">If somebody else is trying to understand it, or if you yourself are looking at it a long time after you wrote it, suitable element names can save a considerable amount of time.</span></span>  
  
## <a name="escaped-names"></a><span data-ttu-id="61c46-123">이스케이프 된 이름</span><span class="sxs-lookup"><span data-stu-id="61c46-123">Escaped Names</span></span>  

 <span data-ttu-id="61c46-124">일반적으로 요소 이름은 Visual Basic에 예약 된 키워드 (예: 또는)와 일치 하지 않아야 `Case` 합니다 `Friend` .</span><span class="sxs-lookup"><span data-stu-id="61c46-124">Generally, an element name must not match any of the keywords reserved by Visual Basic, such as `Case` or `Friend`.</span></span> <span data-ttu-id="61c46-125">그러나 대괄호 ()로 묶인 *이스케이프 된 이름을* 정의할 수 있습니다 `[ ]` .</span><span class="sxs-lookup"><span data-stu-id="61c46-125">However, you can define an *escaped name*, which is enclosed by brackets (`[ ]`).</span></span> <span data-ttu-id="61c46-126">괄호는 모호성을 제거 하므로 이스케이프 된 이름은 모든 Visual Basic 키워드와 일치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61c46-126">An escaped name can match any Visual Basic keyword, since the brackets remove any ambiguity.</span></span> <span data-ttu-id="61c46-127">또한 코드에서 나중에 이름을 참조할 때 괄호를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c46-127">You also use the brackets when you refer to the name later in your code.</span></span>  
  
 <span data-ttu-id="61c46-128">일반적으로 다음과 같은 경우에만 이스케이프 된 이름을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c46-128">In general, you should use escaped names only when:</span></span>  
  
- <span data-ttu-id="61c46-129">코드를 이름으로 사용 되는 키워드를 예약 하지 않은 Visual Basic 이전 버전에서 마이그레이션 했습니다. 디스크나</span><span class="sxs-lookup"><span data-stu-id="61c46-129">Your code has migrated from a previous version of Visual Basic that did not reserve the keyword being used as a name; or</span></span>  
  
- <span data-ttu-id="61c46-130">지정 된 키워드가 예약 되지 않은 다른 언어로 작성 된 코드로 작업 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61c46-130">You are working with code written in another language in which the given keyword is not reserved.</span></span>  
  
 <span data-ttu-id="61c46-131">그렇지 않으면 요소의 이름이 키워드와 충돌 하는 경우 요소의 이름을 바꾸는 것을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c46-131">Otherwise, you should consider renaming the element if its name conflicts with a keyword.</span></span> <span data-ttu-id="61c46-132">IDE (통합 개발 환경)는이 작업을 수행 하는 쉬운 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c46-132">The integrated development environment (IDE) provides an easy way to do this.</span></span> <span data-ttu-id="61c46-133">자세한 내용은 [리팩터링](/visualstudio/ide/refactoring-in-visual-studio)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="61c46-133">For more information, see [Refactoring](/visualstudio/ide/refactoring-in-visual-studio).</span></span>  
  
## <a name="case-sensitivity-in-names"></a><span data-ttu-id="61c46-134">이름에서 대/소문자 구분</span><span class="sxs-lookup"><span data-stu-id="61c46-134">Case Sensitivity in Names</span></span>  

 <span data-ttu-id="61c46-135">Visual Basic의 요소 이름은 대/소문자를 구분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61c46-135">Element names in Visual Basic are case-insensitive.</span></span> <span data-ttu-id="61c46-136">즉, 컴파일러에서 알파벳 대/소문자만 다른 두 이름을 비교할 때 동일한 이름으로 해석 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c46-136">This means that when the compiler compares two names that differ in alphabetic case only, it interprets them as the same name.</span></span> <span data-ttu-id="61c46-137">예를 들어, `ABC` 와 `abc` 는 동일한 선언 요소를 참조하는 것으로 간주합니다.</span><span class="sxs-lookup"><span data-stu-id="61c46-137">For example, it considers `ABC` and `abc` to refer to the same declared element.</span></span>  
  
 <span data-ttu-id="61c46-138">그러나, CLR(공용 언어 런타임)에서는 대/소문자를 구분하는 바인딩을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61c46-138">However, the common language runtime (CLR) uses case-sensitive binding.</span></span> <span data-ttu-id="61c46-139">그러므로, 어셈블리나 DLL을 작성하여 다른 어셈블리에서 이를 사용하게 되면 이름의 대/소문자가 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="61c46-139">Therefore, when you produce an assembly or a DLL and make it available to other assemblies, your names are no longer case-insensitive.</span></span> <span data-ttu-id="61c46-140">예를 들어, `ABC`라는 이름의 요소를 포함하는 클래스를 정의하고 다른 어셈블리에서 공용 언어 런타임을 통해 이 클래스를 사용할 경우 해당 어셈블리에서 이 요소를 `ABC`로 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c46-140">For example, if you define a class with an element called `ABC`, and other assemblies make use of your class through the common language runtime, they must refer to the element as `ABC`.</span></span> <span data-ttu-id="61c46-141">이후에 클래스를 다시 컴파일하고 요소 이름을로 변경 하는 경우 `abc` 클래스를 사용 하는 다른 어셈블리에서 해당 요소에 더 이상 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="61c46-141">If you subsequently recompile your class and change the element's name to `abc`, the other assemblies using your class could no longer access that element.</span></span> <span data-ttu-id="61c46-142">따라서, 어셈블리를 업데이트하여 릴리스하는 경우 공용 요소의 알파벳 대/소문자를 변경하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c46-142">Therefore, when you release an updated version of an assembly, you should not change the alphabetic case of any public elements.</span></span>  
  
## <a name="names-and-locales"></a><span data-ttu-id="61c46-143">이름 및 로캘</span><span class="sxs-lookup"><span data-stu-id="61c46-143">Names and Locales</span></span>  

 <span data-ttu-id="61c46-144">이름 비교는 로캘과 무관 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c46-144">Comparison of names is independent of locale.</span></span> <span data-ttu-id="61c46-145">한 로캘에서 두 이름이 일치 하는 경우 모든 로캘에서 일치 하도록 보장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61c46-145">If two names match in one locale, they are guaranteed to match in all locales.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61c46-146">추가 정보</span><span class="sxs-lookup"><span data-stu-id="61c46-146">See also</span></span>

- [<span data-ttu-id="61c46-147">선언 요소</span><span class="sxs-lookup"><span data-stu-id="61c46-147">Declared Elements</span></span>](index.md)
- [<span data-ttu-id="61c46-148">선언 요소의 특징</span><span class="sxs-lookup"><span data-stu-id="61c46-148">Declared Element Characteristics</span></span>](declared-element-characteristics.md)
- [<span data-ttu-id="61c46-149">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="61c46-149">References to Declared Elements</span></span>](references-to-declared-elements.md)
- [<span data-ttu-id="61c46-150">문</span><span class="sxs-lookup"><span data-stu-id="61c46-150">Statements</span></span>](../../../language-reference/statements/index.md)
