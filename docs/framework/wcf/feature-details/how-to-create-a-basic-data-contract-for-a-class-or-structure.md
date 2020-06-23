---
title: '방법: 클래스 또는 구조체에 대한 기본 데이터 계약 만들기'
description: 다음 예제에 따라 DataContractAttribute 특성을 사용 하 여 WCF의 클래스 또는 구조체를 사용 하 여 데이터 계약을 만드는 방법을 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataMemberAttribute
- DataContractAttribute class
- data contracts [WCF], creating for a class or structure
ms.assetid: bc464889-3070-4a2f-91d2-e788a0f686a7
ms.openlocfilehash: a45fde58795947c3e46fa45750ae1a3faddd8849
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247171"
---
# <a name="how-to-create-a-basic-data-contract-for-a-class-or-structure"></a><span data-ttu-id="6735f-103">방법: 클래스 또는 구조체에 대한 기본 데이터 계약 만들기</span><span class="sxs-lookup"><span data-stu-id="6735f-103">How to: Create a Basic Data Contract for a Class or Structure</span></span>
<span data-ttu-id="6735f-104">이 항목에서는 클래스 또는 구조를 사용하여 데이터 계약을 만드는 기본 단계를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6735f-104">This topic shows the basic steps to create a data contract using a class or structure.</span></span> <span data-ttu-id="6735f-105">데이터 계약 및 사용 방법에 대 한 자세한 내용은 [데이터 계약 사용](using-data-contracts.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6735f-105">For more information about data contracts and how they are used, see [Using Data Contracts](using-data-contracts.md).</span></span>  
  
 <span data-ttu-id="6735f-106">WCF (기본 Windows Communication Foundation) 서비스 및 클라이언트를 만드는 단계를 안내 하는 자습서는 초보자를 위한 [자습서](../getting-started-tutorial.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6735f-106">For a tutorial that walks through the steps of creating a basic Windows Communication Foundation (WCF) service and client, see the [Getting Started Tutorial](../getting-started-tutorial.md).</span></span> <span data-ttu-id="6735f-107">기본 서비스 및 클라이언트로 구성 된 작업 예제 응용 프로그램은 [기본 데이터 계약](../samples/basic-data-contract.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6735f-107">For a working sample application that consists of a basic service and client, see [Basic Data Contract](../samples/basic-data-contract.md).</span></span>  
  
### <a name="to-create-a-basic-data-contract-for-a-class-or-structure"></a><span data-ttu-id="6735f-108">클래스 또는 구조체에 대한 기본 데이터 계약을 만들려면</span><span class="sxs-lookup"><span data-stu-id="6735f-108">To create a basic data contract for a class or structure</span></span>  
  
1. <span data-ttu-id="6735f-109"><xref:System.Runtime.Serialization.DataContractAttribute> 특성을 클래스에 적용하여 형식에 데이터 계약이 있음을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="6735f-109">Declare that the type has a data contract by applying the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to the class.</span></span> <span data-ttu-id="6735f-110">특성이 없는 경우를 비롯한 모든 public 형식을 serialize할 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6735f-110">Note that all public types, including those without attributes, are serializable.</span></span> <span data-ttu-id="6735f-111"><xref:System.Runtime.Serialization.DataContractSerializer> 특성이 없는 경우 <xref:System.Runtime.Serialization.DataContractAttribute>는 데이터 계약을 유추합니다.</span><span class="sxs-lookup"><span data-stu-id="6735f-111">The <xref:System.Runtime.Serialization.DataContractSerializer> infers a data contract if the <xref:System.Runtime.Serialization.DataContractAttribute> attribute is absent.</span></span> <span data-ttu-id="6735f-112">자세한 내용은 [Serializable 형식](serializable-types.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6735f-112">For more information, see [Serializable Types](serializable-types.md).</span></span>  
  
2. <span data-ttu-id="6735f-113"><xref:System.Runtime.Serialization.DataMemberAttribute> 특성을 각 멤버에 적용하여 serialize되는 멤버(속성, 필드 또는 이벤트)를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6735f-113">Define the members (properties, fields, or events) that are serialized by applying the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to each member.</span></span> <span data-ttu-id="6735f-114">이러한 멤버를 데이터 멤버라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="6735f-114">These members are called data members.</span></span> <span data-ttu-id="6735f-115">기본적으로 모든 public 형식을 serialize할 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6735f-115">By default, all public types are serializable.</span></span> <span data-ttu-id="6735f-116">자세한 내용은 [Serializable 형식](serializable-types.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6735f-116">For more information, see [Serializable Types](serializable-types.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="6735f-117"><xref:System.Runtime.Serialization.DataMemberAttribute> 특성을 private 필드에 적용하여 데이터가 다른 사용자에게 노출되게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6735f-117">You can apply the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to private fields, causing the data to be exposed to others.</span></span> <span data-ttu-id="6735f-118">멤버에 중요한 데이터가 포함되지 않도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6735f-118">Be sure that the member does not contain sensitive data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6735f-119">예제</span><span class="sxs-lookup"><span data-stu-id="6735f-119">Example</span></span>  
 <span data-ttu-id="6735f-120">다음 예제에서는 클래스 및 해당 멤버에 `Person` 및 <xref:System.Runtime.Serialization.DataContractAttribute> 특성을 적용하여 <xref:System.Runtime.Serialization.DataMemberAttribute> 형식의 데이터 계약을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6735f-120">The following example shows how to create a data contract for the `Person` type by applying the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes to the class and its members.</span></span>  
  
 [!code-csharp[DataContractAttribute#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/datacontractattribute/cs/overview.cs#2)]
 [!code-vb[DataContractAttribute#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/datacontractattribute/vb/overview.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="6735f-121">참조</span><span class="sxs-lookup"><span data-stu-id="6735f-121">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- [<span data-ttu-id="6735f-122">데이터 계약 사용</span><span class="sxs-lookup"><span data-stu-id="6735f-122">Using Data Contracts</span></span>](using-data-contracts.md)
- [<span data-ttu-id="6735f-123">초보자를 위한 자습서</span><span class="sxs-lookup"><span data-stu-id="6735f-123">Getting Started Tutorial</span></span>](../getting-started-tutorial.md)
- [<span data-ttu-id="6735f-124">시작</span><span class="sxs-lookup"><span data-stu-id="6735f-124">Getting Started</span></span>](../samples/getting-started-sample.md)
