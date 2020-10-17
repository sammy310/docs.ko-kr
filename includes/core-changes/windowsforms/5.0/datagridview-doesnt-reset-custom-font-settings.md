---
ms.openlocfilehash: 9c84c9f844a2a7efb9633c11634b069ef6b6033b
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2020
ms.locfileid: "91804866"
---
### <a name="datagridview-no-longer-resets-fonts-for-customized-cell-styles"></a>DataGridView에서 더 이상 사용자 지정 셀 스타일의 글꼴을 다시 설정하지 않음

앰비언트 글꼴이 변경될 때 <xref:System.Windows.Forms.DataGridViewElement.DataGridView>는 셀 스타일 글꼴이 사용자 지정된 경우 더 이상 기본 셀 스타일 글꼴을 앰비언트 글꼴과 일치하도록 다시 설정하지 않습니다.

#### <a name="change-description"></a>변경 내용 설명

이전 .NET 버전에서 앰비언트 글꼴이 변경되면 <xref:System.Windows.Forms.DataGridViewElement.DataGridView>는 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle>, <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> 속성의 사용자 정의 글꼴을 다시 설정하고 재정의합니다.

.NET 5.0부터 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle> 또는 <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> 속성에 구성한 글꼴 설정은 앰비언트 글꼴이 변경된 경우에도 유지됩니다. 글꼴을 사용자 지정하지 않은 속성의 경우 앰비언트 글꼴 설정과 일치하도록 글꼴이 변경됩니다.

#### <a name="reason-for-change"></a>변경 이유

[.NET Core 3.0에서 기본 글꼴이 변경](../../../../docs/core/compatibility/winforms.md#default-control-font-changed-to-segoe-ui-9-pt)되면서 다양한 셀 스타일의 기본 글꼴 설정도 변경되었습니다. <xref:System.Windows.Forms.DataGridViewElement.DataGridView> 컨트롤에 사용자 지정 스타일을 사용하는 앱에는 바람직한 동작이 아니며 앱을 .NET Framework에서 .NET 5.0으로 마이그레이션하는 데 방해가 됩니다.

#### <a name="version-introduced"></a>도입된 버전

.NET 5.0 RC2

#### <a name="recommended-action"></a>권장 조치

사용자가 수행할 작업은 없습니다. 그러나 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle> 또는 <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> 속성의 글꼴을 사용자 지정했으며 해당 글꼴이 앰비언트 글꼴과 일치하게 하려면 각 속성의 <xref:System.Windows.Forms.DataGridViewCellStyle.Font?displayProperty=nameWithType>을 `null`로 설정합니다.

#### <a name="category"></a>범주

- Windows Forms

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle?displayProperty=fullName>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle?displayProperty=fullName>
- <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Windows.Forms.DataGridView.DefaultCellStyle`
- `P:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle`
- `P:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle`

-->
