---
title: '완화: XML 스키마 유효성 검사'
description: .NET Framework 4.6에서 복합 키를 사용하고 한 개의 키가 비어 있는 경우 XSD 스키마 유효성 검사가 고유한 제약 조건 위반을 검색합니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b73dd4f4-f2dc-47a2-9425-3896e92321fb
ms.openlocfilehash: 0744a703c1e9dc35a8accc448d34f1a736e77e4d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96253533"
---
# <a name="mitigation-xml-schema-validation"></a><span data-ttu-id="d00da-103">완화: XML 스키마 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="d00da-103">Mitigation: XML Schema Validation</span></span>

<span data-ttu-id="d00da-104">.NET Framework 4.6에서 복합 키를 사용하고 한 개의 키가 비어 있는 경우 XSD 스키마 유효성 검사가 고유한 제약 조건 위반을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="d00da-104">In the .NET Framework 4.6, XSD schema validation detects a violation of the unique constraint if a compound key is used and one key is empty.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="d00da-105">영향</span><span class="sxs-lookup"><span data-stu-id="d00da-105">Impact</span></span>  

 <span data-ttu-id="d00da-106">이 변경에 따른 영향이 최소화되어야 합니다. 빈 키가 포함된 복합 키를 사용함으로써 `xsd:unique`가 위반된 경우 스키마 사양에 따라 스키마 유효성 검사 오류가 예상됩니다.</span><span class="sxs-lookup"><span data-stu-id="d00da-106">The impact of this change should be minimal: based on the schema specification, a schema validation error is expected if `xsd:unique` is violated by using a compound key with an empty key.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="d00da-107">완화</span><span class="sxs-lookup"><span data-stu-id="d00da-107">Mitigation</span></span>  

 <span data-ttu-id="d00da-108">복합 키에 한 개의 빈 키가 있는 경우 스키마 유효성 검사 오류 검색 여부는 구성 가능한 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="d00da-108">Whether a schema validation error is detected if a compound key has one empty key is a configurable feature:</span></span>  
  
- <span data-ttu-id="d00da-109">.NET Framework 4.6을 대상으로 하는 앱부터 스키마 유효성 검사 오류 검색은 기본적으로 사용하도록 설정되어 있습니다. 그러나 스키마 유효성 검사 오류가 검색되지 않도록 이 기능을 옵트아웃(opt out)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d00da-109">Starting with the apps that target the .NET Framework 4.6, detection of the schema validation error is enabled by default; however, it is possible to opt out of it, so that the schema validation error will not be detected.</span></span>  
  
- <span data-ttu-id="d00da-110">.NET Framework 4.6에서 실행되지만 .NET Framework 4.5.2 및 이전 버전을 대상으로 하는 앱에서는 스키마 유효성 검사 오류가 기본적으로 검색되지 않습니다. 그러나 스키마 유효성 검사 오류가 검색되도록 이 기능을 옵트인(opt in)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d00da-110">In apps that run under the .NET Framework 4.6 but target the .NET Framework 4.5.2 and earlier versions, a schema validation error is not detected by default; however, it is possible to opt into it, so that the schema validation error will be detected.</span></span>  
  
 <span data-ttu-id="d00da-111">이 동작은 <xref:System.AppContext> 클래스를 사용하여 `System.Xml.IgnoreEmptyKeySequences` 스위치의 값을 정의하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d00da-111">This behavior can be configured by using the <xref:System.AppContext> class to define the value of the `System.Xml.IgnoreEmptyKeySequences` switch.</span></span> <span data-ttu-id="d00da-112">스위치의 기본값은 `false`(빈 키 시퀀스가 무시되지 않음)이기 때문에 .NET Framework 4.6을 대상으로 하는 앱은 다음 코드를 사용하여 스위치의 값을 `true`로 설정하면 해당 동작을 옵트아웃(opt out)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d00da-112">Because the switch's default value is `false` (empty key sequences are not ignored), apps that target the .NET Framework 4.6 can opt out of the behavior by using the following code to set the switch's value to `true`:</span></span>  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#1)]
 [!code-vb[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#1)]  
  
 <span data-ttu-id="d00da-113">.NET Framework 4.5.2 및 이전 버전을 대상으로 하는 앱의 경우 스위치의 기본값이 `true`(빈 키 시퀀스가 무시됨)이기 때문에 다음 코드를 사용하여 스위치의 값을 `false`로 설정하면 빈 키가 포함된 복합 키가 스키마 유효성 검사 오류를 생성하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d00da-113">For apps that target the .NET Framework 4.5.2 and earlier versions, because the switch's default value is `true` (empty key sequences are ignored), it is possible to ensure that a compound key with an empty key does generate a schema validation error by using the following code to set the switch's value to `false`.</span></span>  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#2)]
 [!code-vb[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="d00da-114">참조</span><span class="sxs-lookup"><span data-stu-id="d00da-114">See also</span></span>

- [<span data-ttu-id="d00da-115">애플리케이션 호환성</span><span class="sxs-lookup"><span data-stu-id="d00da-115">Application compatibility</span></span>](application-compatibility.md)
