---
title: 데이터 세트 이벤트 처리
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 54edefe0-bc38-419b-b486-3d8a0c356f13
ms.openlocfilehash: cc425f3217409a154fd319acb8b1555895cbda54
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183366"
---
# <a name="handling-dataset-events"></a>데이터 세트 이벤트 처리

<xref:System.Data.DataSet> 개체는 <xref:System.ComponentModel.MarshalByValueComponent.Disposed>, <xref:System.Data.DataSet.Initialized>및 <xref:System.Data.DataSet.MergeFailed>의 세 가지 이벤트를 제공합니다.  
  
## <a name="the-mergefailed-event"></a>MergeFailed 이벤트  

 `DataSet` 개체의 이벤트 중 가장 많이 사용되는 `MergeFailed`이벤트는 병합하는 `DataSet` 개체의 스키마에서 충돌이 발생할 때 나타납니다. 이러한 충돌은 대상 및 소스 <xref:System.Data.DataRow> 의 기본 키 값이 동일하고 <xref:System.Data.DataSet.EnforceConstraints%2A> 속성이 `true`로 설정된 경우 발생합니다. 예를 들어 병합할 테이블의 기본 키 열이 두 `DataSet` 개체에 있는 테이블 간에서 서로 같으면 예외가 throw되고 `MergeFailed` 이벤트가 발생합니다. <xref:System.Data.MergeFailedEventArgs> 이벤트로 전달되는 `MergeFailed` 개체에는 두 <xref:System.Data.MergeFailedEventArgs.Conflict%2A> 개체 사이의 스키마에서 발생한 충돌을 식별하는 `DataSet` 속성과 충돌한 테이블 이름을 식별하는 <xref:System.Data.MergeFailedEventArgs.Table%2A> 속성이 있습니다.  
  
 다음 코드 단편에서는 `MergeFailed` 이벤트에 대한 이벤트 처리기를 추가하는 방법을 보여 줍니다.  
  
```vb  
AddHandler workDS.MergeFailed, New MergeFailedEventHandler( _  
  AddressOf DataSetMergeFailed)  
  
Private Shared Sub DataSetMergeFailed(  _  
  sender As Object,args As MergeFailedEventArgs)  
  Console.WriteLine("Merge failed for table " & args.Table.TableName)  
  Console.WriteLine("Conflict = " & args.Conflict)  
End Sub  
```  
  
```csharp  
workDS.MergeFailed += new MergeFailedEventHandler(DataSetMergeFailed);  
  
private static void DataSetMergeFailed(  
  object sender, MergeFailedEventArgs args)  
{  
  Console.WriteLine("Merge failed for table " + args.Table.TableName);  
  Console.WriteLine("Conflict = " + args.Conflict);  
}  
```  
  
## <a name="the-initialized-event"></a>Initialized 이벤트  

 <xref:System.Data.DataSet.Initialized> 이벤트는 `DataSet` 생성자가 `DataSet`의 새 인스턴스를 초기화한 후 발생합니다.  
  
 <xref:System.Data.DataSet.IsInitialized%2A> 이 초기화를 완료하면 `true` 속성이 `DataSet` 를 반환하고, 그렇지 않으면 `false`를 반환합니다. <xref:System.Data.DataSet.BeginInit%2A> 의 초기화를 시작하는 `DataSet`메서드는 <xref:System.Data.DataSet.IsInitialized%2A> 를 `false`로 설정하고, <xref:System.Data.DataSet.EndInit%2A> 의 초기화를 끝내는 `DataSet`메서드는 이를 `true`로 설정합니다. 이러한 메서드는 Visual Studio 디자인 환경에서 다른 구성 요소에 사용 되는를 초기화 하는 데 사용 됩니다 `DataSet` . 사용자 코드에는 일반적으로 이러한 메서드를 사용하지 않습니다.  
  
## <a name="the-disposed-event"></a>Disposed 이벤트  

 `DataSet` 은 <xref:System.ComponentModel.MarshalByValueComponent> 메서드와 <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> 이벤트를 모두 노출하는 <xref:System.ComponentModel.MarshalByValueComponent.Disposed> 클래스에서 파생됩니다. <xref:System.ComponentModel.MarshalByValueComponent.Disposed>이벤트는 구성 요소에서 삭제 된 이벤트를 수신 하는 이벤트 처리기를 추가 합니다. <xref:System.ComponentModel.MarshalByValueComponent.Disposed> `DataSet` 메서드가 호출 될 때 코드를 실행 하려는 경우의 이벤트를 사용할 수 있습니다 <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> . <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> 에서 사용 하는 리소스를 해제 <xref:System.ComponentModel.MarshalByValueComponent> 합니다.  
  
> [!NOTE]
> `DataSet`및 `DataTable` 개체는에서 상속 <xref:System.ComponentModel.MarshalByValueComponent> 되며 <xref:System.Runtime.Serialization.ISerializable> 원격을 위해 인터페이스를 지원 합니다. 이 두 개체는 원격으로 연결할 수 있는 유일한 ADO.NET 개체입니다. 자세한 내용은 [.Net Remoting](/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100))을 참조 하십시오.  
  
 로 작업할 때 사용할 수 있는 다른 이벤트에 대 한 자세한 내용은 `DataSet` [DataTable 이벤트 처리](handling-datatable-events.md) 및 [DataAdapter 이벤트 처리](../handling-dataadapter-events.md)를 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- [DataSets, DataTables 및 DataViews](index.md)
- [데이터 유효성 검사](/previous-versions/visualstudio/visual-studio-2013/t3b36awf(v=vs.120))
- [ADO.NET에서 데이터 검색 및 수정](../retrieving-and-modifying-data.md)
- [ADO.NET 개요](../ado-net-overview.md)
