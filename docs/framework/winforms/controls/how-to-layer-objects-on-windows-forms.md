---
title: 개체 계층화
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, layering
- controls [Windows Forms], layering
- z order
- controls [Windows Forms], positioning
- z-order
ms.assetid: 1acc4281-2976-4715-86f4-bda68134baaf
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 1615b9c4df222edd95cda9bceae622ba6f1d8d78
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736344"
---
# <a name="how-to-layer-objects-on-windows-forms"></a>방법: Windows Forms에서 개체 계층화

복잡 한 사용자 인터페이스를 만들거나 MDI (다중 문서 인터페이스) 폼을 사용 하는 경우 더 복잡 한 UI (사용자 인터페이스)를 만들기 위해 컨트롤 및 자식 폼을 모두 계층화 하는 경우가 많습니다. 그룹의 컨텍스트 내에서 컨트롤과 창을 이동 하 고 추적 하려면 *z 순서*를 조작 합니다. Z 순서는 양식의 z 축 (깊이)을 따라 폼에 있는 컨트롤의 시각적 계층화입니다. Z 순서의 맨 위에 있는 창은 다른 모든 창과 겹칩니다. 다른 모든 창은 z 순서의 맨 아래에 있는 창과 겹칩니다.

## <a name="to-layer-controls-at-design-time"></a>디자인 타임에 컨트롤을 계층화 하려면

1. Visual Studio에서 계층화 하려는 컨트롤을 선택 합니다.

2. **서식** 메뉴에서 **순서**를 선택한 다음 맨 **앞으로 가져오기** 또는 **맨 뒤로 보내기**를 선택 합니다.

## <a name="to-layer-controls-programmatically"></a>프로그래밍 방식으로 컨트롤을 계층화 하려면

<xref:System.Windows.Forms.Control.BringToFront%2A> 및 <xref:System.Windows.Forms.Control.SendToBack%2A> 메서드를 사용 하 여 컨트롤의 z 순서를 조작 합니다.

예를 들어 <xref:System.Windows.Forms.TextBox> 컨트롤 `txtFirstName`다른 컨트롤 아래에 있고 맨 위에 있는 경우 다음 코드를 사용 합니다.

```vb
txtFirstName.BringToFront()
```

```csharp
txtFirstName.BringToFront();
```

```cpp
txtFirstName->BringToFront();
```

> [!NOTE]
> Windows Forms는 *제어 제약*을 지원 합니다. 컨트롤 포함에는 포함 하는 컨트롤 내에 많은 컨트롤을 배치 하는 것이 포함 됩니다 (예: <xref:System.Windows.Forms.GroupBox> 컨트롤 내의 여러 <xref:System.Windows.Forms.RadioButton> 컨트롤). 그런 다음 포함 하는 컨트롤 내에서 컨트롤을 계층화 할 수 있습니다. 그룹 상자를 이동 하면 컨트롤이 내부에 포함 되어 있기 때문에 컨트롤도 이동 합니다.

## <a name="see-also"></a>참조

- [Windows Forms 컨트롤](index.md)
- [개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Windows Forms에 사용할 수 있는 컨트롤](controls-to-use-on-windows-forms.md)
- [기능별 Windows Forms 컨트롤](windows-forms-controls-by-function.md)
