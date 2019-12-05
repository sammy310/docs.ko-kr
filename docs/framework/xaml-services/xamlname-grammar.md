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
ms.openlocfilehash: a1e7a5a03db4a24ed4d13d62899754cfe9e76b56
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837157"
---
# <a name="xamlname-grammar"></a><span data-ttu-id="83603-102">XamlName 문법</span><span class="sxs-lookup"><span data-stu-id="83603-102">XamlName Grammar</span></span>
<span data-ttu-id="83603-103">XamlName Grammar은 편의를 위해 여기에서 재현 되는 XAML 언어 사양 [MS XAML]에 정의 된 특정 문법입니다.</span><span class="sxs-lookup"><span data-stu-id="83603-103">XamlName Grammar is a specific grammar that is defined in the XAML language specification [MS-XAML], which is reproduced here for convenience.</span></span>  
  
## <a name="from-the-xaml-specification"></a><span data-ttu-id="83603-104">XAML 사양에서</span><span class="sxs-lookup"><span data-stu-id="83603-104">From the XAML Specification</span></span>  
 <span data-ttu-id="83603-105">[XamlName] 사양은 문법 검사를 정의 하 여 형식 및 속성에 사용 되는 유효한 기호화 된 식별자 집합을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="83603-105">The [MS-XAML] specification defines the grammar XamlName to identify the set of legal symbolic identifiers used for types and properties.</span></span>  
  
 <span data-ttu-id="83603-106">XamlName 형식의 문자열 값은 다음 문법을 준수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83603-106">String values that are of type XamlName must conform to the following grammar:</span></span>  
  
```xaml  
XamlName ::= NameStartChar ( NameChar )*   
NameStartChar ::= LetterCharacter | '_'   
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter   
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl   
DecimalDigit ::= UnicodeNd   
CombiningCharacter ::= UnicodeMn | UnicodeMc  
```  
  
 <span data-ttu-id="83603-107">유니코드 문자 데이터베이스에 정의 된 다음과 같은 일반 범주 값을 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="83603-107">Which assumes the following general category values as defined in the Unicode Character Database</span></span>  

| <span data-ttu-id="83603-108">유니코드 범주</span><span class="sxs-lookup"><span data-stu-id="83603-108">Unicode category</span></span>   | <span data-ttu-id="83603-109">설명</span><span class="sxs-lookup"><span data-stu-id="83603-109">Description</span></span>                   |
|--------------------|-------------------------------|
| <span data-ttu-id="83603-110">Lu</span><span class="sxs-lookup"><span data-stu-id="83603-110">Lu</span></span>                 | <span data-ttu-id="83603-111">문자, 대문자</span><span class="sxs-lookup"><span data-stu-id="83603-111">Letter, Uppercase</span></span>             |
| <span data-ttu-id="83603-112">Ll</span><span class="sxs-lookup"><span data-stu-id="83603-112">Ll</span></span>                 | <span data-ttu-id="83603-113">문자, 소문자</span><span class="sxs-lookup"><span data-stu-id="83603-113">Letter, Lowercase</span></span>             |
| <span data-ttu-id="83603-114">Lt</span><span class="sxs-lookup"><span data-stu-id="83603-114">Lt</span></span>                 | <span data-ttu-id="83603-115">문자, 제목 스타일</span><span class="sxs-lookup"><span data-stu-id="83603-115">Letter, Titlecase</span></span>             |
| <span data-ttu-id="83603-116">Lm</span><span class="sxs-lookup"><span data-stu-id="83603-116">Lm</span></span>                 | <span data-ttu-id="83603-117">문자, 한정자</span><span class="sxs-lookup"><span data-stu-id="83603-117">Letter, Modifier</span></span>              |
| <span data-ttu-id="83603-118">Lo</span><span class="sxs-lookup"><span data-stu-id="83603-118">Lo</span></span>                 | <span data-ttu-id="83603-119">문자, 기타</span><span class="sxs-lookup"><span data-stu-id="83603-119">Letter, Other</span></span>                 |
| <span data-ttu-id="83603-120">Mn</span><span class="sxs-lookup"><span data-stu-id="83603-120">Mn</span></span>                 | <span data-ttu-id="83603-121">표시, 공백 없음</span><span class="sxs-lookup"><span data-stu-id="83603-121">Mark, Non-Spacing</span></span>             |
| <span data-ttu-id="83603-122">Mc</span><span class="sxs-lookup"><span data-stu-id="83603-122">Mc</span></span>                 | <span data-ttu-id="83603-123">표시, 공백 조합</span><span class="sxs-lookup"><span data-stu-id="83603-123">Mark, Spacing Combining</span></span>       |
| <span data-ttu-id="83603-124">Nd</span><span class="sxs-lookup"><span data-stu-id="83603-124">Nd</span></span>                 | <span data-ttu-id="83603-125">숫자, 10 진수</span><span class="sxs-lookup"><span data-stu-id="83603-125">Number, Decimal</span></span>               |
| <span data-ttu-id="83603-126">Nl</span><span class="sxs-lookup"><span data-stu-id="83603-126">Nl</span></span>                 | <span data-ttu-id="83603-127">숫자, 문자</span><span class="sxs-lookup"><span data-stu-id="83603-127">Number, Letter</span></span>                |
 
 <span data-ttu-id="83603-128">XAML은 속성 및 이벤트 정규화 된 참조와 연결 된 멤버에 사용 되는 두 번째 문법 인 DottedXamlName를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="83603-128">XAML defines a second grammar, DottedXamlName, that is used for property and event qualified references, and also for attached members.</span></span> <span data-ttu-id="83603-129">자세한 내용은 <xref:System.Windows.DependencyProperty> 및 [XAML 개요 (WPF)](../../desktop-wpf/fundamentals/xaml.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="83603-129">For more information, see <xref:System.Windows.DependencyProperty> and [XAML Overview (WPF)](../../desktop-wpf/fundamentals/xaml.md).</span></span>  
  
 <span data-ttu-id="83603-130">DottedXamlName 형식의 문자열 값은 다음 문법을 준수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83603-130">String values that are of type DottedXamlName must conform to the following grammar:</span></span>  
  
```xaml  
DottedXamlName ::= XamlName '.' XamlName  
```  
  
## <a name="remarks"></a><span data-ttu-id="83603-131">주의</span><span class="sxs-lookup"><span data-stu-id="83603-131">Remarks</span></span>  
 <span data-ttu-id="83603-132">전체 사양은 [\[MS XAML\]](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="83603-132">For the complete specification, see [\[MS-XAML\]](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>
