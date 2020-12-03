---
title: '호환성이 손상되는 변경: WinForms 속성은 이제 ArgumentOutOfRangeException을 throw함'
description: 일부 Windows Forms 속성이 잘못된 인수에 대해 ArgumentOutOfRangeException을 throw하는 .NET 5.0의 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 06/18/2020
ms.openlocfilehash: 94593047d16304ce401b23993ad4ca173c10812b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759875"
---
# <a name="winforms-properties-now-throw-argumentoutofrangeexception"></a>WinForms 속성은 이제 ArgumentOutOfRangeException을 throw함

이제 일부 Windows Forms 속성에서는 이전에는 없었던 잘못된 인수에 대한 <xref:System.ArgumentOutOfRangeException>을 throw합니다.

## <a name="change-description"></a>변경 내용 설명

이전에 범위를 벗어난 인수를 전달하면 이 속성은 <xref:System.NullReferenceException>, <xref:System.IndexOutOfRangeException>,<xref:System.ArgumentException>과 같은 다양한 예외를 throw했습니다. .NET 5.0부터 범위를 벗어난 인수를 전달하면 이 속성은 이제 <xref:System.ArgumentOutOfRangeException>을 throw합니다.

<xref:System.ArgumentOutOfRangeException> throw는 .NET 런타임의 동작을 따릅니다. 또한 잘못된 인수를 명확하게 전달하여 디버깅 환경을 개선합니다.

## <a name="version-introduced"></a>도입된 버전

.NET 5.0

## <a name="recommended-action"></a>권장 조치

- 잘못된 인수가 전달되지 않도록 코드를 업데이트합니다.
- 필요한 경우 속성을 설정할 때 <xref:System.ArgumentOutOfRangeException>을 처리합니다.

## <a name="affected-apis"></a>영향을 받는 API

다음 표에서는 영향을 받는 속성 및 매개 변수를 보여줍니다.

> [!div class="mx-tdBreakAll"]
> | 속성 | 매개 변수 이름 | 추가된 버전 |
> |-|-|-|
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.Item(System.Int32)?displayProperty=nameWithType> | `index` | 5.0 미리 보기 5 |
> | <xref:System.Windows.Forms.TreeNode.ImageIndex?displayProperty=nameWithType> | `value` | 5.0 미리 보기 6 |
> | <xref:System.Windows.Forms.TreeNode.SelectedImageIndex?displayProperty=nameWithType> | `value` | 5.0 미리 보기 6 |

<!--

### Affected APIs

- `P:System.Windows.Forms.ListBox.IntegerCollection.Item(System.Int32)`
- `P:System.Windows.Forms.TreeNode.ImageIndex`
- `P:System.Windows.Forms.TreeNode.SelectedImageIndex`

### Category

Windows Forms

-->
