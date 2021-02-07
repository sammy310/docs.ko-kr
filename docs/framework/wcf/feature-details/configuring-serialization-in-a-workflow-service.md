---
description: '자세한 정보: 워크플로 서비스에서 Serialization 구성'
title: 워크플로 서비스에서 Serialization 구성
ms.date: 03/30/2017
ms.assetid: aa70b290-a2ee-4c3c-90ea-d0a7665096ae
ms.openlocfilehash: e268f82fc3c1f65086e3c6b112e481ad8abed070
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99743241"
---
# <a name="configuring-serialization-in-a-workflow-service"></a><span data-ttu-id="079e9-103">워크플로 서비스에서 Serialization 구성</span><span class="sxs-lookup"><span data-stu-id="079e9-103">Configuring Serialization in a Workflow Service</span></span>

<span data-ttu-id="079e9-104">워크플로 서비스는 WCF (Windows Communication Foundation) 서비스 이므로 <xref:System.Runtime.Serialization.DataContractSerializer> (기본값) 또는을 사용 하는 옵션을 사용할 수 있습니다 <xref:System.Xml.Serialization.XmlSerializer> .</span><span class="sxs-lookup"><span data-stu-id="079e9-104">Workflow services are Windows Communication Foundation (WCF) services and so have the option of using either the <xref:System.Runtime.Serialization.DataContractSerializer> (the default) or the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="079e9-105">워크플로가 아닌 서비스를 작성할 때 사용할 직렬화기 형식은 서비스 또는 작업 계약에서 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="079e9-105">When writing non-workflow services the type of serializer to use is specified on the service or operation contract.</span></span> <span data-ttu-id="079e9-106">WCF 워크플로 서비스를 만들 때 이러한 계약은 코드로 지정 하지 않고 런타임에 계약 유추를 통해 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="079e9-106">When creating WCF workflow services you don’t specify these contracts in code, but rather they are generated at runtime by contract inference.</span></span> <span data-ttu-id="079e9-107">계약 유추에 대 한 자세한 내용은  [워크플로에서 계약 사용](using-contracts-in-workflow.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="079e9-107">For more information about contract inference, see  [Using Contracts in Workflow](using-contracts-in-workflow.md).</span></span>  <span data-ttu-id="079e9-108">직렬화기는 <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> 속성을 사용하여 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="079e9-108">The serializer is specified using the <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> property.</span></span> <span data-ttu-id="079e9-109">다음 그림과 같이 디자이너에서 이 속성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="079e9-109">This can be set in the designer as shown in the following illustration.</span></span>  
  
 ![속성 창에서 SerializerOption 속성을 설정 합니다.](./media/configuring-serialization-in-a-workflow-service/setting-serializer-property.png)  
  
 <span data-ttu-id="079e9-111">다음 예제와 같이 코드에서 직렬화기를 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="079e9-111">The serializer can also be set in code as shown in the following example,</span></span>  
  
```csharp  
Receive approveExpense = new Receive  
            {  
                OperationName = "ApproveExpense",  
                CanCreateInstance = true,  
                ServiceContractName = "FinanceService",  
                SerializerOption = SerializerOption.DataContractSerializer,  
                Content = ReceiveContent.Create(new OutArgument<Expense>(expense))  
            };  
```  
  
  <span data-ttu-id="079e9-112">워크플로 서비스에서 알려진 형식도 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="079e9-112">Known types can be specified on Workflow services as well.</span></span> <span data-ttu-id="079e9-113">알려진 형식에 대 한 자세한 내용은 [데이터 계약 알려진 형식](data-contract-known-types.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="079e9-113">For more information about Known Types, see [Data Contract Known Types](data-contract-known-types.md).</span></span> <span data-ttu-id="079e9-114">디자이너나 코드에서 알려진 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="079e9-114">Known types can be specified in the designer or in code.</span></span> <span data-ttu-id="079e9-115">디자이너에서 알려진 형식을 지정 하려면 다음 그림과 같이 작업에 대 한 **속성 창** 에서 knowntypes 속성 옆에 있는 줄임표 단추를 클릭 합니다 <xref:System.ServiceModel.Activities.Receive> .</span><span class="sxs-lookup"><span data-stu-id="079e9-115">To specify known types in the designer, click the ellipsis button next to the KnownTypes property in the **Properties Window** for a <xref:System.ServiceModel.Activities.Receive> activity as shown in the following illustration.</span></span>
  
 ![KnownTypes 속성 대화 상자의 스크린샷](./media/configuring-serialization-in-a-workflow-service/known-types-properties.png)  
  
 <span data-ttu-id="079e9-117">그러면 알려진 형식을 검색 하 고 지정할 수 있는 형식 컬렉션 편집기가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="079e9-117">This displays the Type Collections Editor that allows you to search for and specify known types.</span></span>  
  
 ![유형 컬렉션 편집기의 스크린샷](./media/configuring-serialization-in-a-workflow-service/type-collection-editor.gif)  
  
 <span data-ttu-id="079e9-119">**새 형식 추가** 링크를 클릭 하 고 드롭다운을 사용 하 여 알려진 형식 컬렉션에 추가할 형식을 선택 하거나 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="079e9-119">Click the **Add new type** link and use the drop down to select or search for a type to add to the known types collection.</span></span> <span data-ttu-id="079e9-120">코드에서 알려진 형식을 지정하려면 다음 예제와 같이 <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="079e9-120">To specify known types in code use the <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> property as shown in the following example.</span></span>  
  
```csharp
Receive approveExpense = new Receive  
            {  
                OperationName = "ApproveExpense",  
                CanCreateInstance = true,  
                ServiceContractName = "FinanceService",  
                SerializerOption = SerializerOption.DataContractSerializer,  
                Content = ReceiveContent.Create(new OutArgument<Expense>(expense))  
            };  
            approveExpense.KnownTypes.Add(typeof(Travel));  
            approveExpense.KnownTypes.Add(typeof(Meal));  
```
