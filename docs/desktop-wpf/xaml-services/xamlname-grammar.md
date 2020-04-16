---
title: XamlName 문법
ms.date: 03/30/2017
helpviewer_keywords:
- DottedXamlName grammar [XAML Services]
- grammar [XAML Services], DottedXamlName
- grammar [XAML Services], XamlName
- names in XAML [XAML Services]
- XamlName grammar [XAML Services]
ms.assetid: 11e4cada-41d2-494d-9531-0d3df4dfcbe3
ms.openlocfilehash: 2fc74990b15caaa9b58e6eea5b0212ea22505674
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "81433051"
---
# <a name="xamlname-grammar"></a><span data-ttu-id="78365-102">XamlName 문법</span><span class="sxs-lookup"><span data-stu-id="78365-102">XamlName Grammar</span></span>

<span data-ttu-id="78365-103">XamlName 문법은 XAML 언어 사양 [MS-XAML]에 정의된 특정 문법으로, 편의를 위해 여기에 재현됩니다.</span><span class="sxs-lookup"><span data-stu-id="78365-103">XamlName Grammar is a specific grammar that is defined in the XAML language specification [MS-XAML], which is reproduced here for convenience.</span></span>

## <a name="from-the-xaml-specification"></a><span data-ttu-id="78365-104">XAML 사양에서</span><span class="sxs-lookup"><span data-stu-id="78365-104">From the XAML Specification</span></span>

<span data-ttu-id="78365-105">[MS-XAML] 사양은 형식 및 속성에 사용되는 법적 기호 식별자 집합을 식별하기 위해 문법 XamlName을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="78365-105">The [MS-XAML] specification defines the grammar XamlName to identify the set of legal symbolic identifiers used for types and properties.</span></span>

<span data-ttu-id="78365-106">XamlName 형식의 문자열 값은 다음 문법을 준수해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78365-106">String values that are of type XamlName must conform to the following grammar:</span></span>

```xaml
XamlName ::= NameStartChar ( NameChar )*
NameStartChar ::= LetterCharacter | '_'
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl
DecimalDigit ::= UnicodeNd
CombiningCharacter ::= UnicodeMn | UnicodeMc
```

<span data-ttu-id="78365-107">유니코드 문자 데이터베이스에 정의된 다음과 같은 일반 범주 값을 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="78365-107">Which assumes the following general category values as defined in the Unicode Character Database</span></span>

| <span data-ttu-id="78365-108">유니코드 범주</span><span class="sxs-lookup"><span data-stu-id="78365-108">Unicode category</span></span>   | <span data-ttu-id="78365-109">설명</span><span class="sxs-lookup"><span data-stu-id="78365-109">Description</span></span>                   |
|--------------------|-------------------------------|
| <span data-ttu-id="78365-110">루어</span><span class="sxs-lookup"><span data-stu-id="78365-110">Lu</span></span>                 | <span data-ttu-id="78365-111">문자, 대문자</span><span class="sxs-lookup"><span data-stu-id="78365-111">Letter, Uppercase</span></span>             |
| <span data-ttu-id="78365-112">Ll</span><span class="sxs-lookup"><span data-stu-id="78365-112">Ll</span></span>                 | <span data-ttu-id="78365-113">문자, 소문자</span><span class="sxs-lookup"><span data-stu-id="78365-113">Letter, Lowercase</span></span>             |
| <span data-ttu-id="78365-114">Lt</span><span class="sxs-lookup"><span data-stu-id="78365-114">Lt</span></span>                 | <span data-ttu-id="78365-115">문자, 제목 스타일</span><span class="sxs-lookup"><span data-stu-id="78365-115">Letter, Titlecase</span></span>             |
| <span data-ttu-id="78365-116">Lm</span><span class="sxs-lookup"><span data-stu-id="78365-116">Lm</span></span>                 | <span data-ttu-id="78365-117">문자, 한정자</span><span class="sxs-lookup"><span data-stu-id="78365-117">Letter, Modifier</span></span>              |
| <span data-ttu-id="78365-118">Lo</span><span class="sxs-lookup"><span data-stu-id="78365-118">Lo</span></span>                 | <span data-ttu-id="78365-119">문자, 기타</span><span class="sxs-lookup"><span data-stu-id="78365-119">Letter, Other</span></span>                 |
| <span data-ttu-id="78365-120">Mn</span><span class="sxs-lookup"><span data-stu-id="78365-120">Mn</span></span>                 | <span data-ttu-id="78365-121">마크, 간격이 없는 경우</span><span class="sxs-lookup"><span data-stu-id="78365-121">Mark, Non-Spacing</span></span>             |
| <span data-ttu-id="78365-122">Mc</span><span class="sxs-lookup"><span data-stu-id="78365-122">Mc</span></span>                 | <span data-ttu-id="78365-123">표시, 공백 조합</span><span class="sxs-lookup"><span data-stu-id="78365-123">Mark, Spacing Combining</span></span>       |
| <span data-ttu-id="78365-124">Nd</span><span class="sxs-lookup"><span data-stu-id="78365-124">Nd</span></span>                 | <span data-ttu-id="78365-125">번호, 소수점</span><span class="sxs-lookup"><span data-stu-id="78365-125">Number, Decimal</span></span>               |
| <span data-ttu-id="78365-126">Nl</span><span class="sxs-lookup"><span data-stu-id="78365-126">Nl</span></span>                 | <span data-ttu-id="78365-127">숫자, 문자</span><span class="sxs-lookup"><span data-stu-id="78365-127">Number, Letter</span></span>                |

<span data-ttu-id="78365-128">XAML은 속성 및 이벤트 정규화된 참조및 연결된 멤버에 사용되는 두 번째 문법인 DottedXamlName을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="78365-128">XAML defines a second grammar, DottedXamlName, that is used for property and event qualified references, and also for attached members.</span></span> <span data-ttu-id="78365-129">자세한 내용은 및 <xref:System.Windows.DependencyProperty> [XAML 개요(WPF)를](../fundamentals/xaml.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="78365-129">For more information, see <xref:System.Windows.DependencyProperty> and [XAML Overview (WPF)](../fundamentals/xaml.md).</span></span>

<span data-ttu-id="78365-130">DottedXamlName 형식의 문자열 값은 다음 문법을 준수해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78365-130">String values that are of type DottedXamlName must conform to the following grammar:</span></span>

```xaml
DottedXamlName ::= XamlName '.' XamlName
```

## <a name="remarks"></a><span data-ttu-id="78365-131">설명</span><span class="sxs-lookup"><span data-stu-id="78365-131">Remarks</span></span>

<span data-ttu-id="78365-132">전체 사양은 [ \[MS-XAML\]](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="78365-132">For the complete specification, see [\[MS-XAML\]](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>
