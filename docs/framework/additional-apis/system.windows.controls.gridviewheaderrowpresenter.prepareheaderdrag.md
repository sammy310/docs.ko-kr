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
# <a name="prepareheaderdrag-method"></a>PrepareHeaderDrag 메서드

다시 정렬을 위해 지정 된 열 머리글을 준비 합니다.

```csharp
private void PrepareHeaderDrag(GridViewColumnHeader header, Point pos, Point relativePos, bool cancelInvoke)
```

> [!WARNING]
> 이 메서드는 전용 이며 코드에서 직접 사용할 수 없습니다.
>
> Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 방법을 사용 하는 것을 지원 하지 않습니다.

## <a name="parameters"></a>매개 변수

`header` <xref:System.Windows.Controls.GridViewColumnHeader>\
다시 정렬을 준비할 열 머리글입니다.

`pos` <xref:System.Windows.Point>\
끌기가 시작 되는에 상대적인 위치 <xref:System.Windows.Controls.GridViewHeaderRowPresenter> 입니다.

`relativePos` <xref:System.Windows.Point>\
끌기가 시작 되는에 상대적인 위치 `header` 입니다.

`cancelInvoke` <xref:System.Boolean>\
`true` 다시 정렬을 취소 하려면 그렇지 않으면 `false` 입니다.

## <a name="requirements"></a>요구 사항

**네임스페이스:** <xref:System.Windows.Controls>

**어셈블리:** PresentationFramework.dll

## <a name="see-also"></a>참조

- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
