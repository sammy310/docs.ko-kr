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
# <a name="findheaderbycolumn-method"></a>FindHeaderByColumn 메서드

시각적 트리에서 지정 된 열에 대 한 열 머리글을 찾습니다.

```csharp
private GridViewColumnHeader FindHeaderByColumn(GridViewColumn column)
```

> [!WARNING]
> 이 메서드는 전용 이며 코드에서 직접 사용할 수 없습니다.
>
> Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 방법을 사용 하는 것을 지원 하지 않습니다.

## <a name="parameters"></a>매개 변수

`column` <xref:System.Windows.Controls.GridViewColumn>\
헤더를 찾아서 반환 해야 하는 열입니다.

## <a name="return-value"></a>반환 값

<xref:System.Windows.Controls.GridViewColumnHeader>\
지정 된 열의 머리글 이거나, 지정 된 `null` 열이 없으면입니다.

## <a name="requirements"></a>요구 사항

**네임스페이스:** <xref:System.Windows.Controls>

**어셈블리:** PresentationFramework.dll

## <a name="see-also"></a>참조

- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
