---
title: 컨트롤에서 특성 적용
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], applying attributes
- attributes [Windows Forms], applying
- Windows Forms controls, applying attributes
ms.assetid: af0a3f7f-155b-4ba1-83c4-9cf721331a06
ms.openlocfilehash: b8ecd516cf6bb189c6ad1b208dd8e3a5444f001c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741484"
---
# <a name="how-to-apply-attributes-in-windows-forms-controls"></a>방법: Windows Forms 컨트롤에서 특성 적용
디자인 환경과 올바르게 상호 작용 하 고 런타임에 제대로 실행 되는 구성 요소와 컨트롤을 개발 하려면 클래스 및 멤버에 특성을 올바르게 적용 해야 합니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 사용자 지정 컨트롤에 여러 특성을 사용 하는 방법을 보여 줍니다. 컨트롤은 간단한 로깅 기능을 보여 줍니다. 컨트롤은 데이터 소스에 바인딩될 때 데이터 소스에서 보낸 값을 <xref:System.Windows.Forms.DataGridView> 컨트롤에 표시 합니다. 값이 `Threshold` 속성에 지정 된 값을 초과 하면 `ThresholdExceeded` 이벤트가 발생 합니다.  
  
 `AttributesDemoControl`은 `LogEntry` 클래스를 사용 하 여 값을 기록 합니다. `LogEntry` 클래스는 템플릿 클래스입니다. 즉, 기록 하는 형식에 대해 매개 변수가 있습니다. 예를 들어 `AttributesDemoControl` `float`형식의 값을 기록 하는 경우 각 `LogEntry` 인스턴스가 다음과 같이 선언 되 고 사용 됩니다.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
> `LogEntry`는 임의의 형식에 의해 매개 변수화 되기 때문에 리플렉션을 사용 하 여 매개 변수 형식에 대해 작업 해야 합니다. 임계값 기능이 작동 하려면 매개 변수 형식 `T` <xref:System.IComparable> 인터페이스를 구현 해야 합니다.  
  
 `AttributesDemoControl`를 호스팅하는 폼은 성능 카운터를 주기적으로 쿼리 합니다. 각 값은 적절 한 형식의 `LogEntry` 패키지 되 고 폼의 <xref:System.Windows.Forms.BindingSource>에 추가 됩니다. `AttributesDemoControl`는 데이터 바인딩을 통해 값을 받고 <xref:System.Windows.Forms.DataGridView> 컨트롤에 값을 표시 합니다.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 첫 번째 코드 예제는 `AttributesDemoControl` 구현입니다. 두 번째 코드 예제에서는 `AttributesDemoControl`를 사용 하는 폼을 보여 줍니다.  
  
## <a name="class-level-attributes"></a>클래스 수준 특성  
 일부 특성은 클래스 수준에서 적용 됩니다. 다음 코드 예제에서는 Windows Forms 컨트롤에 일반적으로 적용 되는 특성을 보여 줍니다.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### <a name="typeconverter-attribute"></a>TypeConverter 특성  
 <xref:System.ComponentModel.TypeConverterAttribute>은 일반적으로 사용 되는 다른 클래스 수준 특성입니다. 다음 코드 예제에서는 `LogEntry` 클래스에 대 한 사용을 보여 줍니다. 또한이 예제에서는 `LogEntryTypeConverter`이라고 하는 `LogEntry` 형식에 대 한 <xref:System.ComponentModel.TypeConverter> 구현을 보여 줍니다.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## <a name="member-level-attributes"></a>멤버 수준 특성  
 일부 특성은 멤버 수준에서 적용 됩니다. 다음 코드 예제에서는 Windows Forms 컨트롤의 속성에 일반적으로 적용 되는 몇 가지 특성을 보여 줍니다.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### <a name="ambientvalue-attribute"></a>AmbientValue 특성  
 다음 예제에서는 <xref:System.ComponentModel.AmbientValueAttribute>을 보여 주고 디자인 환경과의 상호 작용을 지 원하는 코드를 보여 줍니다. 이 상호 작용을 *외계*이라고 합니다.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### <a name="databinding-attributes"></a>데이터 바인딩 특성  
 다음 예에서는 복합 데이터 바인딩의 구현을 보여 줍니다. 이전에 표시 된 클래스 수준 <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>는 데이터 바인딩에 사용할 `DataSource` 및 `DataMember` 속성을 지정 합니다. `DataSource` 속성이 바인딩될 형식을 지정 하 <xref:System.ComponentModel.AttributeProviderAttribute>입니다.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
  
- `AttributesDemoControl`를 호스팅하는 폼에는를 빌드하기 위해 `AttributesDemoControl` 어셈블리에 대 한 참조가 필요 합니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.IComparable>
- <xref:System.Windows.Forms.DataGridView>
- [.NET Framework에서 사용자 지정 Windows Forms 컨트롤 개발](developing-custom-windows-forms-controls.md)
- [Windows Forms 컨트롤의 특성](attributes-in-windows-forms-controls.md)
- [방법: DesignerSerializationVisibilityAttribute를 사용 하 여 표준 형식의 컬렉션 Serialize](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))
