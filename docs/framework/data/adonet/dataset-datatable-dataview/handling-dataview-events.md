---
title: DataView 이벤트 처리
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5675663-fc91-4e0d-87a9-481b25b64c0f
ms.openlocfilehash: 6c2e554b7e6bde3e82190f70723f272b0d39a18a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61880037"
---
# <a name="handling-dataview-events"></a>DataView 이벤트 처리
<xref:System.Data.DataView.ListChanged>의 <xref:System.Data.DataView> 이벤트를 사용하여 뷰가 업데이트되었는지 확인할 수 있습니다. 이벤트를 발생시키는 업데이트에는 원본으로 사용하는 테이블에서의 행 추가, 삭제 또는 수정과 원본으로 사용하는 테이블 스키마에서의 열 추가 또는 삭제, 그리고 부모 또는 자식 관계의 변경이 포함됩니다. 합니다 **ListChanged** 이벤트 또한 알려 응용 프로그램의 새 정렬 순서나 필터로 인해 보고 있는 행 목록이 크게 변경 된 경우.  
  
 **ListChanged** 이벤트를 구현 하는 **ListChangedEventHandler** 의 대리자는 <xref:System.ComponentModel> 네임 스페이스 및으로 가져오고 입력를 <xref:System.ComponentModel.ListChangedEventArgs> 개체. 변경 유형을 사용 하 여 발생 한 것을 확인할 수 있습니다는 <xref:System.ComponentModel.ListChangedType> 열거 값을 **ListChangedType** 의 속성을 **ListChangedEventArgs** 개체입니다. 추가 관련 된 변경 내용에 대 한 삭제 또는 이동한 행 추가 되거나 이동한 행의 새 인덱스와 삭제 된 행의 이전 인덱스 액세스할 수 있습니다 사용 하는 **NewIndex** 의 속성을 **ListChangedEventArgs** 개체입니다. 이동한 행의 경우 이동한 행의 이전 인덱스 액세스할 수 있습니다는 **OldIndex** 의 속성을 **ListChangedEventArgs** 개체입니다.  
  
 **DataViewManager** 도 노출를 **ListChanged** 테이블이 추가 되거나 제거 된 경우 또는 경우에 변경 내용이 사용자에 게 알려 주기 위해 이벤트를 **관계** 의 컬렉션을 내부 **데이터 집합**합니다.  
  
 다음 코드 예제에서는 추가 하는 방법을 보여 줍니다.는 **ListChanged** 이벤트 처리기입니다.  
  
```vb  
AddHandler custView.ListChanged, _  
  New System.ComponentModel.ListChangedEventHandler( _  
  AddressOf OnListChanged)  
  
Private Shared Sub OnListChanged( _  
  sender As Object, args As System.ComponentModel.ListChangedEventArgs)  
  Console.WriteLine("ListChanged:")  
  Console.WriteLine(vbTab & "    Type = " & _  
    System.Enum.GetName(args.ListChangedType.GetType(), _  
    args.ListChangedType))  
  Console.WriteLine(vbTab & "OldIndex = " & args.OldIndex)  
  Console.WriteLine(vbTab & "NewIndex = " & args.NewIndex)  
End Sub  
```  
  
```csharp  
custView.ListChanged  += new   
  System.ComponentModel.ListChangedEventHandler(OnListChanged);  
  
protected static void OnListChanged(object sender,   
  System.ComponentModel.ListChangedEventArgs args)  
{  
  Console.WriteLine("ListChanged:");  
  Console.WriteLine("\t    Type = " + args.ListChangedType);  
  Console.WriteLine("\tOldIndex = " + args.OldIndex);  
  Console.WriteLine("\tNewIndex = " + args.NewIndex);  
}  
```  
  
## <a name="see-also"></a>참고자료

- <xref:System.Data.DataView>
- <xref:System.ComponentModel.ListChangedEventHandler>
- [DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
