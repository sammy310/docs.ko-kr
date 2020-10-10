---
title: PrepareHeaderDrag 메서드 (GridViewHeaderRowPresenter)
description: PrepareHeaderDrag 라는 개인 WPF 메서드에 대해 알아봅니다.
ms.date: 09/25/2020
ms.technology: dotnet-wpf
topic_type:
- apiref
api_name:
- System.Windows.Controls.GridViewHeaderRowPresenter.PrepareHeaderDrag
api_location:
- PresentationFramework.dll
api_type:
- Assembly
ms.openlocfilehash: 6d806b8a50de3234cd04198f4ab86621dcd6ede1
ms.sourcegitcommit: eb7e87496f42361b1da98562dd75b516c9d58bbc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2020
ms.locfileid: "91877785"
---
# <a name="prepareheaderdrag-method"></a><span data-ttu-id="47683-103">PrepareHeaderDrag 메서드</span><span class="sxs-lookup"><span data-stu-id="47683-103">PrepareHeaderDrag method</span></span>

<span data-ttu-id="47683-104">다시 정렬을 위해 지정 된 열 머리글을 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="47683-104">Prepares the specified column header for reordering.</span></span>

```csharp
private void PrepareHeaderDrag(GridViewColumnHeader header, Point pos, Point relativePos, bool cancelInvoke)
```

> [!WARNING]
> <span data-ttu-id="47683-105">이 메서드는 전용 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="47683-105">This method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="47683-106">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 방법을 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47683-106">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="parameters"></a><span data-ttu-id="47683-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="47683-107">Parameters</span></span>

<span data-ttu-id="47683-108">`header` <xref:System.Windows.Controls.GridViewColumnHeader></span><span class="sxs-lookup"><span data-stu-id="47683-108">`header` <xref:System.Windows.Controls.GridViewColumnHeader></span></span>\
<span data-ttu-id="47683-109">다시 정렬을 준비할 열 머리글입니다.</span><span class="sxs-lookup"><span data-stu-id="47683-109">The column header to prepare for reordering.</span></span>

<span data-ttu-id="47683-110">`pos` <xref:System.Windows.Point></span><span class="sxs-lookup"><span data-stu-id="47683-110">`pos` <xref:System.Windows.Point></span></span>\
<span data-ttu-id="47683-111">끌기가 시작 되는에 상대적인 위치 <xref:System.Windows.Controls.GridViewHeaderRowPresenter> 입니다.</span><span class="sxs-lookup"><span data-stu-id="47683-111">The position, relative to <xref:System.Windows.Controls.GridViewHeaderRowPresenter>, where the dragging starts.</span></span>

<span data-ttu-id="47683-112">`relativePos` <xref:System.Windows.Point></span><span class="sxs-lookup"><span data-stu-id="47683-112">`relativePos` <xref:System.Windows.Point></span></span>\
<span data-ttu-id="47683-113">끌기가 시작 되는에 상대적인 위치 `header` 입니다.</span><span class="sxs-lookup"><span data-stu-id="47683-113">The position, relative to `header`, where the dragging starts.</span></span>

<span data-ttu-id="47683-114">`cancelInvoke` <xref:System.Boolean></span><span class="sxs-lookup"><span data-stu-id="47683-114">`cancelInvoke` <xref:System.Boolean></span></span>\
<span data-ttu-id="47683-115">`true` 다시 정렬을 취소 하려면 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="47683-115">`true` to cancel the reordering; otherwise, `false`.</span></span>

## <a name="requirements"></a><span data-ttu-id="47683-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="47683-116">Requirements</span></span>

<span data-ttu-id="47683-117">**네임스페이스:** <xref:System.Windows.Controls></span><span class="sxs-lookup"><span data-stu-id="47683-117">**Namespace:** <xref:System.Windows.Controls></span></span>

<span data-ttu-id="47683-118">**어셈블리:** PresentationFramework.dll</span><span class="sxs-lookup"><span data-stu-id="47683-118">**Assembly:** PresentationFramework.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="47683-119">참조</span><span class="sxs-lookup"><span data-stu-id="47683-119">See also</span></span>

- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
