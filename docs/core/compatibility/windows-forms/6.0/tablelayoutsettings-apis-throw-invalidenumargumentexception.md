---
title: '호환성이 손상되는 변경: 일부 TableLayoutSettings 속성이 InvalidEnumArgumentException을 throw함'
description: 이제 일부 TableLayoutSettings API가 잘못된 인수에 대해 InvalidEnumArgumentException을 throw하는 .NET 6.0의 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 01/18/2021
ms.openlocfilehash: 8397952e4647347718f11597a100c5d764e7186b
ms.sourcegitcommit: f8cd3ef517ee177c99feed944824c27d208cc0d1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2021
ms.locfileid: "98570244"
---
# <a name="selected-tablelayoutsettings-properties-throw-invalidenumargumentexception"></a>선택한 TableLayoutSettings 속성이 InvalidEnumArgumentException을 throw함

잘못된 값을 할당하려고 하면 이제 선택한 <xref:System.Windows.Forms.TableLayoutSettings> 속성이 <xref:System.ComponentModel.InvalidEnumArgumentException>을 throw합니다.

## <a name="change-description"></a>변경 내용 설명

이전 .NET 버전에서는 잘못된 값을 할당하려고 하면 해당 속성이 <xref:System.ArgumentOutOfRangeException>을 throw합니다. .NET 6.0부터 해당 속성은 이러한 경우에 <xref:System.ComponentModel.InvalidEnumArgumentException>을 throw합니다.

## <a name="reason-for-change"></a>변경 이유

<xref:System.ComponentModel.InvalidEnumArgumentException>을 throw하는 것은 유사한 상황에서 기존 Windows Forms API에 맞추려는 것입니다. 또한 이 예외를 throw하면 개발자에게 향상된 디버그 환경이 제공됩니다.

## <a name="version-introduced"></a>도입된 버전

.NET 6.0

## <a name="recommended-action"></a>권장 조치

- 잘못된 값이 할당되지 않도록 코드를 업데이트합니다.
- 필요한 경우 이 API에 액세스할 때 <xref:System.ComponentModel.InvalidEnumArgumentException>을 처리합니다.

## <a name="affected-apis"></a>영향을 받는 API

다음 표에서는 영향을 받는 속성을 보여 줍니다.

| 속성 | 버전이 변경됨 |
|-|-|-|-|
| <xref:System.Windows.Forms.TableLayoutPanel.CellBorderStyle?displayProperty=fullName> | 미리 보기 1 |
| <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle?displayProperty=fullName> | 미리 보기 1 |

<!--

### Affected APIs

- `P:System.Windows.Forms.TableLayoutPanel.CellBorderStyle`
- `P:System.Windows.Forms.TableLayoutPanel.GrowStyle`

### Category

Windows Forms

-->
