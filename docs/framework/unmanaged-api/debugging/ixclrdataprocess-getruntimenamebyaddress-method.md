---
description: '자세히 알아보기: IXCLRDataProcess:: GetRuntimeNameByAddress 메서드'
title: 'IXCLRDataProcess:: Getrunti Amebyaddress 메서드'
ms.date: 4/27/2020
api.name:
- IXCLRDataProcess::GetRuntimeNameByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::GetRuntimeNameByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::GetRuntimeNameByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: tommcdon
ms.author: tommcdon
ms.openlocfilehash: 62d9ae73c216748cc8eb02aedd41cf19f475d071
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800658"
---
# <a name="ixclrdataprocessgetruntimenamebyaddress-method"></a>IXCLRDataProcess:: Getrunti Amebyaddress 메서드

지정 된 주소에 대 한 이름을 가져옵니다.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>구문

```cpp
HRESULT GetRuntimeNameByAddress(
    [in] CLRDATA_ADDRESS address,
    [in] ULONG32 flags,
    [in] ULONG32 bufLen,
    [out] ULONG32 *nameLen,
    [out, size_is(bufLen)] WCHAR nameBuf[],
    [out] CLRDATA_ADDRESS* displacement
);
```

## <a name="parameters"></a>매개 변수

`address`\
진행 `CLRDATA_ADDRESS` 코드 주소를 나타내는 값입니다.

`flags`\
진행 ' 0 '으로 설정 합니다.

`bufLen`\
진행 버퍼의 길이입니다.

`namLen`\
제한이 반환 된 문자 수에 대 한 포인터입니다.

`namBuf`\
[out, size_is ( `bufLen` )] `bufLen` 런타임 이름을 저장 하는 길이의 입력 버퍼입니다.

`displacement`\
제한이 `CLRDATA_ADDRESS` 반환 된 기호의 코드 오프셋에 대 한 포인터입니다.

## <a name="remarks"></a>설명

제공 된 메서드는 인터페이스의 일부 이며 `IXCLRDataProcess` 가상 메서드 테이블의 16 번째 슬롯에 해당 합니다.

> [!NOTE]
> 버퍼가 이름에 대해 충분히 크지 않은 경우이 메서드는를 반환 하 `S_FALSE` 고 `nameLen` 를 필요한 버퍼 길이로 설정 합니다.

## <a name="requirements"></a>요구 사항

**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md) 을 참조 하세요.\
**헤더:** 없음을
**라이브러리:** 없음을
**.NET Framework 버전:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]

## <a name="see-also"></a>참고 항목

- [디버깅](index.md)
- [IXCLRDataProcess 인터페이스](ixclrdataprocess-interface.md)
