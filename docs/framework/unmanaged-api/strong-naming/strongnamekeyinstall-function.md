---
title: StrongNameKeyInstall 함수
ms.date: 03/30/2017
api_name:
- StrongNameKeyInstall
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyInstall
helpviewer_keywords:
- StrongNameKeyInstall function [.NET Framework strong naming]
ms.assetid: e32fd546-7757-4681-be3d-658e93281e50
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7121ace6777e7cf947fcc6ff30b1ea314851feff
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636711"
---
# <a name="strongnamekeyinstall-function"></a>StrongNameKeyInstall 함수

공개/개인 키 쌍을 컨테이너로 가져옵니다.

이 함수는 더 이상 사용 되지 않습니다. 사용 된 [iclrstrongname:: Strongnamekeyinstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md) 메서드 대신 합니다.

## <a name="syntax"></a>구문

```cpp
BOOLEAN StrongNameKeyInstall (
    [in]  LPCWSTR   wszKeyContainer,
    [in]  BYTE      *pbKeyBlob,
    [in]  ULONG     cbKeyBlob
);
```

## <a name="parameters"></a>매개 변수

`wszKeyContainer`\
[in] 키 컨테이너의 이름입니다. `wszKeyContainer` 비어 있지 않은 문자열 이어야 합니다.

`pbKeyBlob`\
[in] 이진 키 쌍입니다.

`cbKeyBlob`\
[in] 크기 (바이트)의 `pbKeyBlob`합니다.

## <a name="return-value"></a>반환 값

`true` 성공적으로 완료 됩니다. 그렇지 않으면 `false`합니다.

## <a name="remarks"></a>설명

사용 된 [StrongNameKeyDelete](strongnamekeydelete-function.md) 키 컨테이너를 삭제 하는 함수입니다.

경우는 `StrongNameKeyInstall` 함수가 성공적으로 완료으로 호출 되지 않으면 합니다 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 마지막 생성 된 오류를 검색 하는 함수입니다.

## <a name="requirements"></a>요구 사항

**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.

**헤더:** StrongName.h

**라이브러리:** MsCorEE.dll에 리소스로 포함

**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>참고자료

- [StrongNameKeyInstall 메서드](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [StrongNameKeyDelete 메서드](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [ICLRStrongName 인터페이스](../hosting/iclrstrongname-interface.md)
