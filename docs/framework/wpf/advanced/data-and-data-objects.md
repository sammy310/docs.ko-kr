---
title: 데이터 및 데이터 개체
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data transfer [WPF], drag-and-drop
- DataFormats class [WPF]
- DataObject class [WPF]
ms.assetid: 5967d557-1867-420f-a524-ae3af78402da
ms.openlocfilehash: 532c254f997da183b073ddc9e00b4364ecfcd739
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186345"
---
# <a name="data-and-data-objects"></a>데이터 및 데이터 개체
끌어서 놓기 작업의 일부로 전송되는 데이터는 데이터 개체에 저장됩니다.  개념적으로 데이터 개체는 다음 쌍 중 하나 이상으로 구성됩니다.  
  
- 실제 <xref:System.Object> 데이터를 포함하는 A.  
  
- 해당 데이터 형식 식별자입니다.  
  
 데이터 자체는 기본으로 <xref:System.Object>나타낼 수 있는 모든 것으로 구성될 수 있습니다.  해당 데이터 형식은 문자열이거나 <xref:System.Type> 데이터가 있는 형식에 대한 힌트를 제공합니다.  데이터 개체는 여러 데이터/데이터 형식 쌍 호스팅을 지원합니다. 이렇게 하면 단일 데이터 개체가 여러 형식으로 데이터를 제공할 수 있습니다.  
  
<a name="Data_and_Data_Objects"></a>
## <a name="data-objects"></a>데이터 개체  
 모든 데이터 개체는 <xref:System.Windows.IDataObject> 데이터 전송을 가능하게 하고 용이하게 하는 다음과 같은 표준 메서드 집합을 제공하는 인터페이스를 구현해야 합니다.  
  
|방법|요약|  
|------------|-------------|  
|<xref:System.Windows.IDataObject.GetData%2A>|지정된 데이터 형식의 데이터 개체를 검색합니다.|  
|<xref:System.Windows.IDataObject.GetDataPresent%2A>|지정된 형식의 데이터가 있거나 지정된 형식으로 변환될 수 있는지 확인합니다.|  
|<xref:System.Windows.IDataObject.GetFormats%2A>|이 데이터 개체의 데이터가 저장되거나 변환될 수 있는 형식 목록을 반환합니다.|  
|<xref:System.Windows.IDataObject.SetData%2A>|이 데이터 개체에 지정된 데이터를 저장합니다.|  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]클래스에서 <xref:System.Windows.IDataObject> 기본 구현을 <xref:System.Windows.DataObject> 제공합니다. stock <xref:System.Windows.DataObject> 클래스는 많은 일반적인 데이터 전송 시나리오에 충분합니다.  
  
 비트맵, CSV, 파일, HTML, RTF, 문자열, 텍스트 및 오디오와 같은 몇 가지 미리 정의된 형식이 있습니다. 함께 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]제공되는 미리 정의된 데이터 형식에 대한 <xref:System.Windows.DataFormats> 자세한 내용은 클래스 참조 항목을 참조하십시오.  
  
 데이터 개체에는 일반적으로 데이터를 추출하는 동안 한 형식으로 저장된 데이터를 다른 형식으로 자동으로 변환하는 기능이 포함됩니다. 이 기능을 자동 변환이라고 합니다. <xref:System.Windows.DataObject.GetFormats%28System.Boolean%29> 데이터 개체에서 사용할 수 있는 데이터 형식을 쿼리할 때 자동 변환 가능한 데이터 형식을 호출하거나 <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> 메서드를 호출하고 `autoConvert` 매개 `false`변수를 로 지정하여 네이티브 데이터 형식에서 필터링할 수 있습니다.  메서드를 <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%2CSystem.Boolean%29> 사용하여 데이터 개체에 데이터를 추가할 때 매개 변수를 로 `autoConvert` 설정하여 데이터의 자동 변환을 금지할 `false`수 있습니다.  
  
<a name="Working_with_Data_Objects"></a>
## <a name="working-with-data-objects"></a>데이터 개체 작업  
 이 섹션에서는 데이터 개체를 만들고 작업하는 일반적인 기술에 대해 설명합니다.  
  
### <a name="creating-new-data-objects"></a>새 데이터 개체 만들기  
 클래스는 <xref:System.Windows.DataObject> 단일 데이터/데이터 형식 쌍으로 새 <xref:System.Windows.DataObject> 인스턴스를 쉽게 채울 수 있는 여러 오버로드된 생성자 제공 합니다.  
  
 다음 예제 코드는 새 데이터 개체를 만들고 오버로드된 <xref:System.Windows.DataObject.%23ctor%2A><xref:System.Windows.DataObject.%23ctor(System.String,System.Object)>생성자 () 중 하나를 사용하여 문자열 및 지정된 데이터 형식으로 데이터 개체를 초기화합니다.  이 경우 데이터 형식은 문자열로 지정됩니다. 클래스는 <xref:System.Windows.DataFormats> 미리 정의된 형식 문자열 집합을 제공합니다. 저장된 데이터의 자동 변환은 기본적으로 허용됩니다.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
 데이터 개체를 만드는 코드의 자세한 예는 [데이터 개체 만들기](how-to-create-a-data-object.md)를 참조하십시오.  
  
### <a name="storing-data-in-multiple-formats"></a>여러 형식으로 데이터 저장  
 단일 데이터 개체는 데이터를 여러 형식으로 저장할 수 있습니다.   단일 데이터 개체 내에서 여러 데이터 형식을 전략적으로 사용하면 단일 데이터 형식만 나타낼 수 있는 경우보다 훨씬 다양한 놓기 대상에서 데이터 개체를 사용할 수 있습니다.  일반적으로 드래그 소스는 잠재적인 놓기 대상에 의해 소모품인 데이터 형식에 대해 독립적이어야 합니다.  
  
 다음 예제에서는 메서드를 <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29> 사용하여 여러 형식으로 데이터 개체에 데이터를 추가하는 방법을 보여 주며 있습니다.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_storemultipleformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_storemultipleformats)]  
  
### <a name="querying-a-data-object-for-available-formats"></a>사용 가능한 형식에 대한 데이터 개체 쿼리  
 단일 데이터 개체에는 임의의 수의 데이터 형식이 포함될 수 있으므로 데이터 개체에는 사용 가능한 데이터 형식 목록을 검색하는 시설이 포함됩니다.  
  
 다음 예제 코드는 <xref:System.Windows.DataObject.GetFormats%2A> 오버로드를 사용하여 데이터 개체에서 사용할 수 있는 모든 데이터 형식을 나타내는 문자열 배열을 가져옵니다(네이티브 및 자동 변환).  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
 사용 가능한 데이터 형식에 대한 데이터 개체를 쿼리하는 코드의 자세한 예는 [데이터 개체의 데이터 형식 목록을](how-to-list-the-data-formats-in-a-data-object.md)참조하십시오.  특정 데이터 형식이 있는지 데이터 개체를 쿼리하는 예는 [데이터 형식이 데이터 개체에 있는지 확인을](how-to-determine-if-a-data-format-is-present-in-a-data-object.md)참조하십시오.  
  
### <a name="retrieving-data-from-a-data-object"></a>데이터 개체에서 데이터 검색  
 특정 형식의 데이터 개체에서 데이터를 검색하려면 <xref:System.Windows.DataObject.GetData%2A> 메서드 중 하나를 호출하고 원하는 데이터 형식을 지정하기만 하면 됩니다.  방법 <xref:System.Windows.DataObject.GetDataPresent%2A> 중 하나는 특정 데이터 형식의 존재를 확인하는 데 사용할 수 있습니다.  <xref:System.Windows.DataObject.GetData%2A>에서 데이터를 반환합니다. <xref:System.Object> 데이터 형식에 따라 이 개체를 형식별 컨테이너로 캐스팅할 수 있습니다.  
  
 다음 예제 코드는 <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> 오버로드를 사용하여 지정된 데이터 형식을 사용할 수 있는지(기본 또는 자동 변환)를 확인합니다. 지정된 형식을 사용할 수 있는 경우 예제에서는 <xref:System.Windows.DataObject.GetData%28System.String%29> 메서드를 사용하여 데이터를 검색합니다.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
 데이터 개체에서 데이터를 검색하는 코드의 자세한 예는 [특정 데이터 형식의 데이터 검색](how-to-retrieve-data-in-a-particular-data-format.md)을 참조하십시오.  
  
### <a name="removing-data-from-a-data-object"></a>데이터 개체에서 데이터 제거  
 데이터 개체에서 데이터를 직접 제거할 수 없습니다.  데이터 개체에서 데이터를 효과적으로 제거하려면 다음 단계를 따르십시오.  
  
1. 유지하려는 데이터만 포함하는 새 데이터 개체를 만듭니다.  
  
2. 이전 데이터 개체에서 원하는 데이터를 새 데이터 개체로 "복사"합니다.  데이터를 복사하려면 <xref:System.Windows.DataObject.GetData%2A> 메서드 중 하나를 사용하여 <xref:System.Object> 원시 데이터가 포함된 메서드를 검색한 <xref:System.Windows.DataObject.SetData%2A> 다음 메서드 중 하나를 사용하여 새 데이터 개체에 데이터를 추가합니다.  
  
3. 이전 데이터 개체를 새 데이터 개체로 바꿉습니다.  
  
> [!NOTE]
> 메서드는 <xref:System.Windows.DataObject.SetData%2A> 데이터 개체에만 데이터를 추가합니다. 데이터 및 데이터 형식이 이전 호출과 정확히 동일하더라도 데이터를 대체하지 않습니다. 동일한 <xref:System.Windows.DataObject.SetData%2A> 데이터 및 데이터 형식에 대해 두 번 호출하면 데이터/데이터 형식이 데이터 개체에 두 번 표시됩니다.
