---
title: 워크플로 서비스에서 Serialization 구성
ms.date: 03/30/2017
ms.assetid: aa70b290-a2ee-4c3c-90ea-d0a7665096ae
ms.openlocfilehash: 5076f3d377a656cb96909cf8df01591dc6ab72b7
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597542"
---
# <a name="configuring-serialization-in-a-workflow-service"></a>워크플로 서비스에서 Serialization 구성
워크플로 서비스는 WCF (Windows Communication Foundation) 서비스 이므로 <xref:System.Runtime.Serialization.DataContractSerializer> (기본값) 또는을 사용 하는 옵션을 사용할 수 있습니다 <xref:System.Xml.Serialization.XmlSerializer> . 워크플로가 아닌 서비스를 작성할 때 사용할 직렬화기 형식은 서비스 또는 작업 계약에서 지정됩니다. WCF 워크플로 서비스를 만들 때 이러한 계약은 코드로 지정 하지 않고 런타임에 계약 유추를 통해 생성 됩니다. 계약 유추에 대 한 자세한 내용은 [워크플로에서 계약 사용](using-contracts-in-workflow.md)을 참조 하세요.  직렬화기는 <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> 속성을 사용하여 지정됩니다. 다음 그림과 같이 디자이너에서 이 속성을 설정할 수 있습니다.  
  
 ![속성 창에서 SerializerOption 속성을 설정 합니다.](./media/configuring-serialization-in-a-workflow-service/setting-serializer-property.png)  
  
 다음 예제와 같이 코드에서 직렬화기를 설정할 수도 있습니다.  
  
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
  
  워크플로 서비스에서 알려진 형식도 지정할 수 있습니다. 알려진 형식에 대 한 자세한 내용은 [데이터 계약 알려진 형식](data-contract-known-types.md)을 참조 하세요. 디자이너나 코드에서 알려진 형식을 지정할 수 있습니다. 디자이너에서 알려진 형식을 지정 하려면 다음 그림과 같이 작업에 대 한 **속성 창** 에서 knowntypes 속성 옆에 있는 줄임표 단추를 클릭 합니다 <xref:System.ServiceModel.Activities.Receive> .
  
 ![KnownTypes 속성 대화 상자의 스크린샷](./media/configuring-serialization-in-a-workflow-service/known-types-properties.png)  
  
 그러면 알려진 형식을 검색 하 고 지정할 수 있는 형식 컬렉션 편집기가 표시 됩니다.  
  
 ![유형 컬렉션 편집기의 스크린샷](./media/configuring-serialization-in-a-workflow-service/type-collection-editor.gif)  
  
 **새 형식 추가** 링크를 클릭 하 고 드롭다운을 사용 하 여 알려진 형식 컬렉션에 추가할 형식을 선택 하거나 검색 합니다. 코드에서 알려진 형식을 지정하려면 다음 예제와 같이 <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> 속성을 사용합니다.  
  
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
