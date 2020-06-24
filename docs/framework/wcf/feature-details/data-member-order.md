---
title: 데이터 멤버 순서
description: WCF의 데이터 멤버 순서에 대해 알아봅니다. 응용 프로그램은 데이터 멤버가 전송 되거나 예상 되는 순서를 확인 하거나 변경 해야 할 수 있습니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data contracts [WCF], ordering members
ms.assetid: 0658a47d-b6e5-4ae0-ba72-ababc3c6ff33
ms.openlocfilehash: 5c192d3bda65a7364345df4310dccd96cbe04056
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247366"
---
# <a name="data-member-order"></a><span data-ttu-id="7fb34-104">데이터 멤버 순서</span><span class="sxs-lookup"><span data-stu-id="7fb34-104">Data Member Order</span></span>
<span data-ttu-id="7fb34-105">일부 애플리케이션에서는 serialize된 XML로 표시되는 데이터 순서와 같이 여러 데이터 멤버로부터 데이터가 전송 또는 수신되는 순서를 알고 있는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb34-105">In some applications, it is useful to know the order in which data from the various data members is sent or is expected to be received (such as the order in which data appears in the serialized XML).</span></span> <span data-ttu-id="7fb34-106">이 순서는 경우에 따라 변경해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb34-106">Sometimes it may be necessary to change this order.</span></span> <span data-ttu-id="7fb34-107">이 항목에서는 순서 지정 규칙에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb34-107">This topic explains the ordering rules.</span></span>  
  
## <a name="basic-rules"></a><span data-ttu-id="7fb34-108">기본 규칙</span><span class="sxs-lookup"><span data-stu-id="7fb34-108">Basic Rules</span></span>  
 <span data-ttu-id="7fb34-109">데이터의 순서를 지정하는 기본 규칙은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb34-109">The basic rules for data ordering include:</span></span>  
  
- <span data-ttu-id="7fb34-110">데이터 계약 형식이 상속 계층 구조의 일부이면 기본 형식의 데이터 멤버가 항상 첫 번째 순서입니다.</span><span class="sxs-lookup"><span data-stu-id="7fb34-110">If a data contract type is a part of an inheritance hierarchy, data members of its base types are always first in the order.</span></span>  
  
- <span data-ttu-id="7fb34-111">그 다음 순서는 <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> 특성 집합의 <xref:System.Runtime.Serialization.DataMemberAttribute> 속성을 갖고 있지 않은 현재 형식의 데이터 멤버(사전순)입니다.</span><span class="sxs-lookup"><span data-stu-id="7fb34-111">Next in order are the current type’s data members that do not have the <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> property of the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute set, in alphabetical order.</span></span>  
  
- <span data-ttu-id="7fb34-112">그리고 <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> 특성 집합의 <xref:System.Runtime.Serialization.DataMemberAttribute> 속성을 가진 데이터 멤버가 그 다음 순서입니다.</span><span class="sxs-lookup"><span data-stu-id="7fb34-112">Next are any data members that have the <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> property of the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute set.</span></span> <span data-ttu-id="7fb34-113">이러한 멤버의 순서는 먼저 `Order` 속성 값으로 지정되고, 둘 이상의 멤버가 특정 `Order` 값을 갖고 있으면 사전순으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fb34-113">These are ordered by the value of the `Order` property first and then alphabetically if there is more than one member of a certain `Order` value.</span></span> <span data-ttu-id="7fb34-114">순서 값을 무시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb34-114">Order values may be skipped.</span></span>  
  
 <span data-ttu-id="7fb34-115">사전순은 <xref:System.String.CompareOrdinal%2A> 메서드 호출로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fb34-115">Alphabetical order is established by calling the <xref:System.String.CompareOrdinal%2A> method.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="7fb34-116">예제</span><span class="sxs-lookup"><span data-stu-id="7fb34-116">Examples</span></span>  
 <span data-ttu-id="7fb34-117">다음과 같은 코드를 생각해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb34-117">Consider the following code.</span></span>  
  
 [!code-csharp[C_DataContractNames#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#4)]
 [!code-vb[C_DataContractNames#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#4)]  
  
 <span data-ttu-id="7fb34-118">XML은 다음과 유사하게 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fb34-118">The XML produced is similar to the following.</span></span>  
  
```xml  
<DerivedType>  
    <!-- Zebra is a base data member, and appears first. -->  
    <zebra/>
  
    <!-- Cat has no Order, appears alphabetically first. -->  
    <cat/>  
  
   <!-- Dog has no Order, appears alphabetically last. -->  
    <dog/>
  
    <!-- Bird is the member with the smallest Order value -->  
    <bird/>  
  
    <!-- Albatross has the next Order value, alphabetically first. -->  
    <albatross/>  
  
    <!-- Parrot, with the next Order value, alphabetically last. -->  
     <parrot/>  
  
    <!-- Antelope is the member with the highest Order value. Note that   
    Order=2 is skipped -->  
     <antelope/>
</DerivedType>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7fb34-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7fb34-119">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractAttribute>
- [<span data-ttu-id="7fb34-120">데이터 계약 동등성</span><span class="sxs-lookup"><span data-stu-id="7fb34-120">Data Contract Equivalence</span></span>](data-contract-equivalence.md)
- [<span data-ttu-id="7fb34-121">데이터 계약 사용</span><span class="sxs-lookup"><span data-stu-id="7fb34-121">Using Data Contracts</span></span>](using-data-contracts.md)
