---
title: 데이터 계약 동등성
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data contracts [WCF], equivalence
ms.assetid: f06f3c7e-c235-4ec1-b200-68142edf1ed1
ms.openlocfilehash: 2a8c186c839be5008bbc5315c7c9fae638680714
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293925"
---
# <a name="data-contract-equivalence"></a><span data-ttu-id="9a8b6-102">데이터 계약 동등성</span><span class="sxs-lookup"><span data-stu-id="9a8b6-102">Data Contract Equivalence</span></span>

<span data-ttu-id="9a8b6-103">클라이언트가 서비스에 특정 형식의 데이터를 성공적으로 보내거나, 서비스에서 클라이언트에 데이터를 성공적으로 보내기 위해, 보낸 형식이 받는 측에 반드시 있어야 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="9a8b6-103">For a client to successfully send data of a certain type to a service, or a service to successfully send data to a client, the sent type does not necessarily have to exist on the receiving end.</span></span> <span data-ttu-id="9a8b6-104">두 형식의 데이터 계약이 일치하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a8b6-104">The only requirement is that the data contracts of both types be equivalent.</span></span> <span data-ttu-id="9a8b6-105">( [데이터 계약 버전 관리](data-contract-versioning.md)에 설명 된 대로 엄격한 동등성이 필요 하지 않은 경우도 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="9a8b6-105">(Sometimes, strict equivalence is not required, as discussed in [Data Contract Versioning](data-contract-versioning.md).)</span></span>  
  
 <span data-ttu-id="9a8b6-106">데이터 계약이 서로 같으려면 네임스페이스와 이름이 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a8b6-106">For data contracts to be equivalent, they must have the same namespace and name.</span></span> <span data-ttu-id="9a8b6-107">또한 한 쪽의 각 데이터 멤버에 해당하는 데이터 멤버가 다른 쪽에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a8b6-107">Additionally, each data member on one side must have an equivalent data member on the other side.</span></span>  
  
 <span data-ttu-id="9a8b6-108">데이터 멤버가 같으려면 이름이 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a8b6-108">For data members to be equivalent, they must have the same name.</span></span> <span data-ttu-id="9a8b6-109">또한 데이터 멤버가 동일한 형식의 데이터를 나타내야 합니다. 즉, 해당 데이터 계약이 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a8b6-109">Additionally, they must represent the same type of data; that is, their data contracts must be equivalent.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9a8b6-110">데이터 계약 이름 및 네임스페이스와 데이터 멤버 이름은 대/소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="9a8b6-110">Note that data contract names and namespaces, as well as data member names, are case-sensitive.</span></span>  
  
 <span data-ttu-id="9a8b6-111">데이터 계약 이름 및 네임 스페이스 뿐만 아니라 데이터 멤버 이름에 대 한 자세한 내용은 [데이터 계약 이름](data-contract-names.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9a8b6-111">For more information about data contract names and namespaces, as well as data member names, see [Data Contract Names](data-contract-names.md).</span></span>  
  
 <span data-ttu-id="9a8b6-112">같은 쪽(발신자 또는 수신자)에 두 가지 형식이 있고 해당 데이터 계약이 다른 경우(예: 데이터 멤버가 서로 다른 경우) 동일한 이름과 네임스페이스를 지정하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a8b6-112">If two types exist on the same side (sender or receiver) and their data contracts are not equivalent (for example, they have different data members), you should not give them the same name and namespace.</span></span> <span data-ttu-id="9a8b6-113">그렇게 하면 예외가 throw될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a8b6-113">Doing so may cause exceptions to be thrown.</span></span>  
  
 <span data-ttu-id="9a8b6-114">다음 형식에 대한 데이터 계약은 서로 동등합니다.</span><span class="sxs-lookup"><span data-stu-id="9a8b6-114">The data contracts for the following types are equivalent:</span></span>  
  
 [!code-csharp[C_DataContractNames#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#5)]
 [!code-vb[C_DataContractNames#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#5)]  
  
## <a name="data-member-order-and-data-contract-equivalence"></a><span data-ttu-id="9a8b6-115">데이터 멤버 주문 및 데이터 계약 동등성</span><span class="sxs-lookup"><span data-stu-id="9a8b6-115">Data Member Order and Data Contract equivalence</span></span>  

 <span data-ttu-id="9a8b6-116"><xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> 클래스의 <xref:System.Runtime.Serialization.DataMemberAttribute> 속성을 사용하여 데이터 계약 동등성에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a8b6-116">Using the <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> property of the <xref:System.Runtime.Serialization.DataMemberAttribute> class may affect data contract equivalence.</span></span> <span data-ttu-id="9a8b6-117">데이터 계약이 서로 동등하려면 멤버가 동일한 순서로 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a8b6-117">The data contracts must have members that appear in the same order to be equivalent.</span></span> <span data-ttu-id="9a8b6-118">기본 순서는 사전순입니다.</span><span class="sxs-lookup"><span data-stu-id="9a8b6-118">The default order is alphabetical.</span></span> <span data-ttu-id="9a8b6-119">자세한 내용은 [데이터 멤버 순서](data-member-order.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9a8b6-119">For more information, see [Data Member Order](data-member-order.md).</span></span>  
  
 <span data-ttu-id="9a8b6-120">예를 들어, 다음 코드는 동등한 데이터 계약을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9a8b6-120">For example, the following code results in equivalent data contracts.</span></span>  
  
 [!code-csharp[C_DataContractNames#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#6)]
 [!code-vb[C_DataContractNames#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#6)]  
  
 <span data-ttu-id="9a8b6-121">다음 코드는 동등한 데이터 계약을 생성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9a8b6-121">However, the following does not result in an equivalent data contract.</span></span>  
  
 [!code-csharp[C_DataContractNames#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#7)]
 [!code-vb[C_DataContractNames#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#7)]  
  
## <a name="inheritance-interfaces-and-data-contract-equivalence"></a><span data-ttu-id="9a8b6-122">상속, 인터페이스 및 데이터 계약 동등성</span><span class="sxs-lookup"><span data-stu-id="9a8b6-122">Inheritance, Interfaces, and Data Contract Equivalence</span></span>  

 <span data-ttu-id="9a8b6-123">동등성을 결정할 때 다른 데이터 계약으로부터 상속되는 데이터 계약은 기본 형식의 모든 데이터 멤버를 포함하는 데이터 계약처럼 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a8b6-123">When determining equivalence, a data contract that inherits from another data contract is treated as if it is just one data contract that includes all of the data members from the base type.</span></span> <span data-ttu-id="9a8b6-124">데이터 멤버의 순서가 일치해야 하고, 기본 형식 멤버가 파생된 형식 멤버보다 앞에 와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a8b6-124">Keep in mind that the order of the data members must match and that base type members precede derived type members in the order.</span></span> <span data-ttu-id="9a8b6-125">또한 다음 코드 예제에서처럼 두 데이터 멤버의 순서 값이 동일한 경우 해당 데이터 멤버의 순서는 사전순으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a8b6-125">Furthermore, if, as in the following code example, two data members have the same order value, the ordering for those data members is alphabetical.</span></span> <span data-ttu-id="9a8b6-126">자세한 내용은 [데이터 멤버 순서](data-member-order.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9a8b6-126">For more information, see [Data Member Order](data-member-order.md).</span></span>  
  
 <span data-ttu-id="9a8b6-127">다음 예제에서 `Employee` 형식 데이터 계약은 `Worker` 형식 데이터 계약과 동등합니다.</span><span class="sxs-lookup"><span data-stu-id="9a8b6-127">In the following example, the data contract for type `Employee` is equivalent to the data contract for the type `Worker`.</span></span>  
  
 [!code-csharp[C_DataContractNames#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractnames/cs/source.cs#8)]
 [!code-vb[C_DataContractNames#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractnames/vb/source.vb#8)]  
  
 <span data-ttu-id="9a8b6-128">클라이언트와 서비스 간에 매개 변수 및 반환 값을 전달할 때 수신하는 엔드포인트에 파생된 클래스의 데이터 계약이 필요한 경우 기본 클래스의 데이터 계약을 보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9a8b6-128">When passing parameters and return values between a client and a service, a data contract from a base class cannot be sent when the receiving endpoint expects a data contract from a derived class.</span></span> <span data-ttu-id="9a8b6-129">이는 개체 지향 프로그래밍 개념을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="9a8b6-129">This is in accordance with object-oriented programming tenets.</span></span> <span data-ttu-id="9a8b6-130">이전 예제에서는 `Person` 가 예상 될 때 형식의 개체를 보낼 수 없습니다 `Employee` .</span><span class="sxs-lookup"><span data-stu-id="9a8b6-130">In the previous example, an object of type `Person` cannot be sent when an `Employee` is expected.</span></span>  
  
 <span data-ttu-id="9a8b6-131">기본 클래스의 데이터 계약이 필요한 경우에 파생 클래스의 데이터 계약을 보낼 수 있지만, 수신하는 엔드포인트가 <xref:System.Runtime.Serialization.KnownTypeAttribute>를 사용하여 파생 형식에 대해 "알고 있는" 경우에만 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a8b6-131">A data contract from a derived class can be sent when a data contract from a base class is expected, but only if the receiving endpoint "knows" of the derived type using the <xref:System.Runtime.Serialization.KnownTypeAttribute>.</span></span> <span data-ttu-id="9a8b6-132">자세한 내용은 [데이터 계약 알려진 형식을](data-contract-known-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9a8b6-132">For more information, see [Data Contract Known Types](data-contract-known-types.md).</span></span> <span data-ttu-id="9a8b6-133">이전 예제에서 `Employee`이 필요할 때 `Person` 형식 개체를 보낼 수 있지만, 수신기 코드에서 <xref:System.Runtime.Serialization.KnownTypeAttribute>를 사용하여 알려진 형식 목록에 포함시키는 경우에만 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a8b6-133">In the previous example, an object of type `Employee` can be sent when a `Person` is expected, but only if the receiver code employs the <xref:System.Runtime.Serialization.KnownTypeAttribute> to include it in the list of known types.</span></span>  
  
 <span data-ttu-id="9a8b6-134">애플리케이션 간에 매개 변수 및 반환 값을 전달할 때 필요한 형식이 인터페이스이면 <xref:System.Object> 형식의 예상 형식과 동등합니다.</span><span class="sxs-lookup"><span data-stu-id="9a8b6-134">When passing parameters and return values between applications, if the expected type is an interface, it is equivalent to the expected type being of type <xref:System.Object>.</span></span> <span data-ttu-id="9a8b6-135">모든 형식이 궁극적으로 <xref:System.Object>에서 파생되기 때문에 모든 데이터 계약은 궁극적으로 <xref:System.Object>에 대한 데이터 계약에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a8b6-135">Because every type ultimately derives from <xref:System.Object>, every data contract ultimately derives from the data contract for <xref:System.Object>.</span></span> <span data-ttu-id="9a8b6-136">따라서 인터페이스가 필요할 때 모든 데이터 계약 형식을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a8b6-136">Thus, any data contract type can be passed when an interface is expected.</span></span> <span data-ttu-id="9a8b6-137">인터페이스를 성공적으로 사용 하려면 추가 단계가 필요 합니다. 자세한 내용은 [데이터 계약 알려진 형식](data-contract-known-types.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9a8b6-137">Additional steps are required to successfully work with interfaces; for more information, see [Data Contract Known Types](data-contract-known-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a8b6-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9a8b6-138">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- [<span data-ttu-id="9a8b6-139">데이터 멤버 순서</span><span class="sxs-lookup"><span data-stu-id="9a8b6-139">Data Member Order</span></span>](data-member-order.md)
- [<span data-ttu-id="9a8b6-140">데이터 계약 알려진 형식</span><span class="sxs-lookup"><span data-stu-id="9a8b6-140">Data Contract Known Types</span></span>](data-contract-known-types.md)
- [<span data-ttu-id="9a8b6-141">데이터 계약 이름</span><span class="sxs-lookup"><span data-stu-id="9a8b6-141">Data Contract Names</span></span>](data-contract-names.md)
