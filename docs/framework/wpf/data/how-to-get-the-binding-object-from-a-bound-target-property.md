---
title: '방법: 바인딩된 대상 속성에서 바인딩 개체 가져오기'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], getting binding objects from bound target properties
- properties [WPF], getting binding objects from
ms.assetid: 87974c5f-136b-4de7-b07d-9285b62ab123
ms.openlocfilehash: c528515124898c7deb6114e620ce21766123ab3c
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453054"
---
# <a name="how-to-get-the-binding-object-from-a-bound-target-property"></a>방법: 바인딩된 대상 속성에서 바인딩 개체 가져오기
이 예제에서는 데이터 바인딩된 대상 속성에서 바인딩 개체를 가져오는 방법을 보여 줍니다.

## <a name="example"></a>예제
 다음 작업을 수행 하 여 <xref:System.Windows.Data.Binding> 개체를 가져올 수 있습니다.

 [!code-csharp[BindValidation#GetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml.cs#getbinding)]

> [!NOTE]
> 대상 개체의 둘 이상의 속성이 데이터 바인딩을 사용하고 있을 수 있으므로 원하는 바인딩에 대한 종속성 속성을 지정해야 합니다.

 또는 <xref:System.Windows.Data.BindingExpression> 가져온 다음 <xref:System.Windows.Data.BindingExpression.ParentBinding%2A> 속성의 값을 가져올 수 있습니다.

 전체 예제는 [Binding Validation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/BindValidation)(바인딩 유효성 검사 샘플)을 참조하세요.

> [!NOTE]
> 바인딩이 <xref:System.Windows.Data.MultiBinding>경우 <xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A?displayProperty=nameWithType>를 사용 합니다. <xref:System.Windows.Data.PriorityBinding>경우 <xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A?displayProperty=nameWithType>를 사용 합니다. <xref:System.Windows.Data.Binding>, <xref:System.Windows.Data.MultiBinding>또는 <xref:System.Windows.Data.PriorityBinding>를 사용 하 여 대상 속성이 바인딩되어 있는지 확실 하지 않으면 <xref:System.Windows.Data.BindingOperations.GetBindingBase%2A?displayProperty=nameWithType>를 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목

- [코드에서 바인딩 만들기](how-to-create-a-binding-in-code.md)
- [방법 항목](data-binding-how-to-topics.md)
