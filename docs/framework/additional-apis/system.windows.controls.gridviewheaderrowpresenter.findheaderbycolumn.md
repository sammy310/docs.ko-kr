---
title: FindHeaderByColumn 메서드 (GridViewHeaderRowPresenter)
description: FindHeaderByColumn 이라는 개인 WPF 메서드에 대해 알아봅니다.
ms.date: 09/25/2020
ms.technology: dotnet-wpf
topic_type:
- apiref
api_name:
- System.Windows.Controls.GridViewHeaderRowPresenter.FindHeaderByColumn
api_location:
- PresentationFramework.dll
api_type:
- Assembly
ms.openlocfilehash: 88ed2928f86602d1078488354de6d5267c0311f5
ms.sourcegitcommit: eb7e87496f42361b1da98562dd75b516c9d58bbc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2020
ms.locfileid: "91877800"
---
# <a name="findheaderbycolumn-method"></a><span data-ttu-id="53adb-103">FindHeaderByColumn 메서드</span><span class="sxs-lookup"><span data-stu-id="53adb-103">FindHeaderByColumn method</span></span>

<span data-ttu-id="53adb-104">시각적 트리에서 지정 된 열에 대 한 열 머리글을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="53adb-104">Finds the column header for the specified column in the visual tree.</span></span>

```csharp
private GridViewColumnHeader FindHeaderByColumn(GridViewColumn column)
```

> [!WARNING]
> <span data-ttu-id="53adb-105">이 메서드는 전용 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="53adb-105">This method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="53adb-106">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 방법을 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="53adb-106">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="parameters"></a><span data-ttu-id="53adb-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="53adb-107">Parameters</span></span>

<span data-ttu-id="53adb-108">`column` <xref:System.Windows.Controls.GridViewColumn></span><span class="sxs-lookup"><span data-stu-id="53adb-108">`column` <xref:System.Windows.Controls.GridViewColumn></span></span>\
<span data-ttu-id="53adb-109">헤더를 찾아서 반환 해야 하는 열입니다.</span><span class="sxs-lookup"><span data-stu-id="53adb-109">The column whose header should be found and returned.</span></span>

## <a name="return-value"></a><span data-ttu-id="53adb-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="53adb-110">Return value</span></span>

<xref:System.Windows.Controls.GridViewColumnHeader>\
<span data-ttu-id="53adb-111">지정 된 열의 머리글 이거나, 지정 된 `null` 열이 없으면입니다.</span><span class="sxs-lookup"><span data-stu-id="53adb-111">The header of the specified column, or `null` if the specified column doesn't exist.</span></span>

## <a name="requirements"></a><span data-ttu-id="53adb-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="53adb-112">Requirements</span></span>

<span data-ttu-id="53adb-113">**네임스페이스:** <xref:System.Windows.Controls></span><span class="sxs-lookup"><span data-stu-id="53adb-113">**Namespace:** <xref:System.Windows.Controls></span></span>

<span data-ttu-id="53adb-114">**어셈블리:** PresentationFramework.dll</span><span class="sxs-lookup"><span data-stu-id="53adb-114">**Assembly:** PresentationFramework.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="53adb-115">참조</span><span class="sxs-lookup"><span data-stu-id="53adb-115">See also</span></span>

- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
