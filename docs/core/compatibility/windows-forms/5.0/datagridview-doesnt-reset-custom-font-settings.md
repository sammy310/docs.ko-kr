---
title: '호환성이 손상되는 변경: DataGridView에서 더 이상 사용자 지정 셀 스타일의 글꼴을 다시 설정하지 않음'
description: 셀 스타일 글꼴이 사용자 지정된 경우 DataGridView에서 더 이상 앰비언트 글꼴과 일치하도록 기본 셀 스타일 글꼴을 다시 설정하지 않는 .NET 5의 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 10/18/2020
ms.openlocfilehash: fd28fb5a0b508157289dde1b720522ed49163e31
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256130"
---
# <a name="datagridview-no-longer-resets-fonts-for-customized-cell-styles"></a><span data-ttu-id="5baf2-103">DataGridView에서 더 이상 사용자 지정 셀 스타일의 글꼴을 다시 설정하지 않음</span><span class="sxs-lookup"><span data-stu-id="5baf2-103">DataGridView no longer resets fonts for customized cell styles</span></span>

<span data-ttu-id="5baf2-104">앰비언트 글꼴이 변경될 때 <xref:System.Windows.Forms.DataGridViewElement.DataGridView>는 셀 스타일 글꼴이 사용자 지정된 경우 더 이상 기본 셀 스타일 글꼴을 앰비언트 글꼴과 일치하도록 다시 설정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5baf2-104">When the ambient font changes, <xref:System.Windows.Forms.DataGridViewElement.DataGridView> no longer resets default cell style fonts to match the ambient font if the cell style font has been customized.</span></span>

## <a name="change-description"></a><span data-ttu-id="5baf2-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="5baf2-105">Change description</span></span>

<span data-ttu-id="5baf2-106">이전 .NET 버전에서 앰비언트 글꼴이 변경되면 <xref:System.Windows.Forms.DataGridViewElement.DataGridView>는 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle>, <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> 속성의 사용자 정의 글꼴을 다시 설정하고 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5baf2-106">In previous .NET versions, if the ambient font changes, <xref:System.Windows.Forms.DataGridViewElement.DataGridView> resets and overrides user-defined fonts in the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle>, and <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> properties.</span></span>

<span data-ttu-id="5baf2-107">.NET 5부터 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle> 또는 <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> 속성에 구성한 글꼴 설정은 앰비언트 글꼴이 변경된 경우에도 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="5baf2-107">Starting in .NET 5, if you configure font settings in the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle>, or <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> properties, those settings are retained even when the ambient font changes.</span></span> <span data-ttu-id="5baf2-108">글꼴을 사용자 지정하지 않은 속성의 경우 앰비언트 글꼴 설정과 일치하도록 글꼴이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="5baf2-108">For any of these properties that you don't customize the font, the font will change to match the ambient font settings.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="5baf2-109">변경 이유</span><span class="sxs-lookup"><span data-stu-id="5baf2-109">Reason for change</span></span>

<span data-ttu-id="5baf2-110">[.NET Core 3.0에서 기본 글꼴이 변경](../../winforms.md#default-control-font-changed-to-segoe-ui-9-pt)되면서 다양한 셀 스타일의 기본 글꼴 설정도 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5baf2-110">With the [change of the default font in .NET Core 3.0](../../winforms.md#default-control-font-changed-to-segoe-ui-9-pt), the default font settings for the various cell styles also changed.</span></span> <span data-ttu-id="5baf2-111"><xref:System.Windows.Forms.DataGridViewElement.DataGridView> 컨트롤에 사용자 지정 스타일을 사용하는 앱에는 바람직한 동작이 아니며 앱을 .NET Framework에서 .NET 5.0으로 마이그레이션하는 데 방해가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5baf2-111">This behavior is undesirable for apps that rely on custom styling in their <xref:System.Windows.Forms.DataGridViewElement.DataGridView> controls, and impeded the migration of these apps from .NET Framework to .NET 5.0.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="5baf2-112">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="5baf2-112">Version introduced</span></span>

<span data-ttu-id="5baf2-113">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="5baf2-113">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="5baf2-114">권장 조치</span><span class="sxs-lookup"><span data-stu-id="5baf2-114">Recommended action</span></span>

<span data-ttu-id="5baf2-115">사용자가 수행할 작업은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5baf2-115">No action is required on your part.</span></span> <span data-ttu-id="5baf2-116">그러나 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle> 또는 <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> 속성의 글꼴을 사용자 지정했으며 해당 글꼴이 앰비언트 글꼴과 일치하게 하려면 각 속성의 <xref:System.Windows.Forms.DataGridViewCellStyle.Font?displayProperty=nameWithType>을 `null`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5baf2-116">However, if you've customized the font in the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle>, or <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> properties and want the font to match the ambient font, set <xref:System.Windows.Forms.DataGridViewCellStyle.Font?displayProperty=nameWithType> to `null` for each property.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="5baf2-117">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="5baf2-117">Affected APIs</span></span>

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle?displayProperty=fullName>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle?displayProperty=fullName>
- <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle?displayProperty=fullName>

<!--

### Affected APIs

- `P:System.Windows.Forms.DataGridView.DefaultCellStyle`
- `P:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle`
- `P:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle`

### Category

- Windows Forms

-->
