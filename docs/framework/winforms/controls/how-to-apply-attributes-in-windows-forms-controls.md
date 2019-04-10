---
title: '방법: Windows Forms 컨트롤에서 특성 적용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], applying attributes
- attributes [Windows Forms], applying
- Windows Forms controls, applying attributes
ms.assetid: af0a3f7f-155b-4ba1-83c4-9cf721331a06
ms.openlocfilehash: e86277c06e515b28bada3331cf4fd63e536319a4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59079593"
---
# <a name="how-to-apply-attributes-in-windows-forms-controls"></a>방법: Windows Forms 컨트롤에서 특성 적용
구성 요소 및 디자인 환경은와 제대로 상호 작용을 런타임에 제대로 실행 하는 컨트롤을 개발 하려면 클래스 및 멤버에 특성을 올바르게 적용 해야 합니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 사용자 지정 컨트롤에 여러 특성을 사용 하는 방법에 설명 합니다. 컨트롤에는 간단한 로깅 기능을 보여 줍니다. 컨트롤이 데이터 소스에 바인딩된, 데이터 원본에 의해 전송 되는 값 표시를 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 값에 지정 된 값을 초과 하는 경우는 `Threshold` 속성을 `ThresholdExceeded` 이벤트가 발생 합니다.  
  
 합니다 `AttributesDemoControl` 값을 기록를 `LogEntry` 클래스입니다. `LogEntry` 클래스는 템플릿 클래스는 기록 하는 형식 매개 변수화 됩니다. 예를 들어 경우는 `AttributesDemoControl` 로깅 값 형식의 `float`각각 `LogEntry` 인스턴스를 선언 하 고 다음과 같이 사용 합니다.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
>  때문에 `LogEntry` 매개 변수화 된 임의의 형식에 의해 매개 변수 형식에 적용할 리플렉션을 사용 해야 합니다. 작업, 매개 변수 형식이 임계값 기능에 대 한 `T` 구현 해야 합니다는 <xref:System.IComparable> 인터페이스입니다.  
  
 호스팅하는 폼을 `AttributesDemoControl` 성능 카운터를 주기적으로 쿼리 합니다. 각 값에 패키지를 `LogEntry` 적절 한 형식의 폼에 추가한 <xref:System.Windows.Forms.BindingSource>합니다. 합니다 `AttributesDemoControl` 해당 데이터 바인딩을 통해 값을 수신 하 고 값을 표시는 <xref:System.Windows.Forms.DataGridView> 제어 합니다.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 첫 번째 코드 예는 `AttributesDemoControl` 구현 합니다. 두 번째 코드 예제에 사용 하는 폼을 `AttributesDemoControl`입니다.  
  
## <a name="class-level-attributes"></a>클래스 수준 특성  
 일부 특성은 클래스 수준에서 적용 됩니다. 다음 코드 예제에서는 일반적으로 Windows Forms 컨트롤에 적용 되는 특성을 보여 줍니다.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### <a name="typeconverter-attribute"></a>TypeConverter 특성  
 <xref:System.ComponentModel.TypeConverterAttribute> 자주 사용 되는 다른 클래스 수준 특성이입니다. 다음 코드 예제에 대 한 용도 보여 줍니다.는 `LogEntry` 클래스입니다. 구현을 보여이 줍니다는 <xref:System.ComponentModel.TypeConverter> 에 대 한 합니다 `LogEntry` 이라는 형식을 `LogEntryTypeConverter`합니다.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## <a name="member-level-attributes"></a>멤버 수준 특성  
 일부 특성은 멤버 수준에서 적용 됩니다. 다음 코드 예제에서는 일반적으로 Windows Forms 컨트롤의 속성에 적용 되는 일부 특성을 표시 합니다.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### <a name="ambientvalue-attribute"></a>AmbientValue 특성  
 다음 예제는 <xref:System.ComponentModel.AmbientValueAttribute> 의 디자인 환경 상호 작용을 지 원하는 코드를 보여 줍니다. 이러한 상호 작용 라고 *앰 비 언스*합니다.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### <a name="databinding-attributes"></a>데이터 바인딩 특성  
 다음 예제에서는 복잡 한 데이터 바인딩 구현을 보여 줍니다. 클래스 수준 <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>표시 된 이전에 지정 합니다 `DataSource` 및 `DataMember` 데이터 바인딩을 사용 하는 속성입니다. <xref:System.ComponentModel.AttributeProviderAttribute> 대상 형식 지정을 `DataSource` 속성 바인딩합니다.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
  
-   호스팅하는 폼의 `AttributesDemoControl` 에 대 한 참조가 필요는 `AttributesDemoControl` 빌드하려면 어셈블리.  
  
## <a name="see-also"></a>참고자료

- <xref:System.IComparable>
- <xref:System.Windows.Forms.DataGridView>
- [.NET Framework에서 사용자 지정 Windows Forms 컨트롤 개발](developing-custom-windows-forms-controls.md)
- [Windows Forms 컨트롤의 특성](attributes-in-windows-forms-controls.md)
- [방법: Designerserializationvisibilityattribute를 사용 하 여 표준 형식의 컬렉션 serialize](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))
