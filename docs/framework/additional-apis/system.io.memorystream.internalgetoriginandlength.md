---
description: 'MemoryStream에 대 한 자세한 정보: InternalGetOriginAndLength 메서드'
title: MemoryStream InternalGetOriginAndLength 메서드 (System.IO)
ms.date: 11/19/2019
topic_type:
- apiref
api_name:
- System.IO.MemoryStream.InternalGetOriginAndLength
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: 4232852c0835a43454f36271a43062e1240297a5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802543"
---
# <a name="memorystreaminternalgetoriginandlength-method"></a>MemoryStream.InternalGetOriginAndLength 메서드

원본 및 메모리 스트림의 길이에 대 한 내부 값을 가져옵니다.

```csharp
internal void InternalGetOriginAndLength(out int origin, out int length)
```

## <a name="parameters"></a>매개 변수

- `origin` <xref:System.Int32>\
  이 메서드가 반환 될 때 새 개체를 만들 때 지정 된 바이트 배열의 오프셋입니다 <xref:System.IO.MemoryStream> . 에서 바이트 배열을 만든 경우 0을 포함 <xref:System.IO.MemoryStream> 합니다.

- `length` <xref:System.Int32>\
  이 메서드가 반환 될 때 메모리 스트림 내의 바이트 수입니다.

## <a name="remarks"></a>설명

> [!WARNING]
> `MemoryStream.InternalGetOriginAndLength`메서드는 내부 이며 코드에서 직접 사용할 수 없습니다.
>
> Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 방법을 사용 하는 것을 지원 하지 않습니다.

## <a name="requirements"></a>요구 사항

**네임스페이스:** <xref:System.IO>

**어셈블리:** mscorlib.dll (mscorlib.dll)

**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.
