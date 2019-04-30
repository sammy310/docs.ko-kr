---
title: StrongNameKeyDelete 함수
ms.date: 03/30/2017
api_name:
- StrongNameKeyDelete
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyDelete
helpviewer_keywords:
- StrongNameKeyDelete function [.NET Framework strong naming]
ms.assetid: 313e71e4-1790-4d2f-b68b-5040ebd1c149
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dfc785a48d0cdf1cf2fdc0245a27b8ef35fd2d81
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62040770"
---
# <a name="strongnamekeydelete-function"></a>StrongNameKeyDelete 함수

지정된 키 컨테이너를 삭제합니다.

이 함수는 더 이상 사용 되지 않습니다. 사용 된 [iclrstrongname:: Strongnamekeydelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) 메서드 대신 합니다.

## <a name="syntax"></a>구문

```cpp
BOOLEAN StrongNameKeyDelete (
    [in]  LPCWSTR   wszKeyContainer
);
```

## <a name="parameters"></a>매개 변수

`wszKeyContainer`\
[in] 삭제할 키 컨테이너의 이름입니다.

## <a name="return-value"></a>반환 값

`true` 성공적으로 완료 됩니다. 그렇지 않으면 `false`합니다.

## <a name="remarks"></a>설명

사용 합니다 [StrongNameKeyInstall](strongnamekeyinstall-function.md) 컨테이너로 공개/개인 키 쌍을 가져오는 함수입니다.

경우는 `StrongNameKeyDelete` 함수가 성공적으로 완료으로 호출 되지 않으면 합니다 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 마지막 생성 된 오류를 검색 하는 함수입니다.

## <a name="requirements"></a>요구 사항

**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.

**헤더:** StrongName.h

**라이브러리:** MsCorEE.dll에 리소스로 포함

**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>참고자료

- [StrongNameKeyDelete 메서드](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [StrongNameKeyInstall 메서드](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [ICLRStrongName 인터페이스](../hosting/iclrstrongname-interface.md)