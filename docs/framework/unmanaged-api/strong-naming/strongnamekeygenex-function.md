---
title: StrongNameKeyGenEx 함수
ms.date: 03/30/2017
api_name:
- StrongNameKeyGenEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyGenEx
helpviewer_keywords:
- StrongNameKeyGenEx function [.NET Framework strong naming]
ms.assetid: 36bd10b9-9857-45f3-8d3b-0da091d6169e
topic_type:
- apiref
ms.openlocfilehash: 63ddd90f3a8090853d10f03052915d10e1503ea6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125212"
---
# <a name="strongnamekeygenex-function"></a>StrongNameKeyGenEx 함수
강력한 이름 사용을 위해 지정 된 키 크기를 사용 하 여 새 공개/개인 키 쌍을 생성 합니다.  
  
 이 함수는 더 이상 사용 되지 않습니다. 대신 [ICLRStrongName:: StrongNameKeyGenEx](../hosting/iclrstrongname-strongnamekeygenex-method.md) 메서드를 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
BOOLEAN StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `wszKeyContainer`  
 진행 요청 된 키 컨테이너 이름입니다. `wszKeyContainer`은 비어 있지 않은 문자열 이거나 null 이거나 임시 이름을 생성 하는 null 이어야 합니다.  
  
 `dwFlags`  
 진행 키를 등록 된 상태로 유지할지 여부를 지정 합니다. 다음 값이 지원 됩니다.  
  
- 0x00000000-임시 키 컨테이너 이름을 생성 하기 위해 `wszKeyContainer`가 null 일 때 사용 됩니다.  
  
- 0x00000001 (`SN_LEAVE_KEY`)-키를 등록 된 상태로 유지 하도록 지정 합니다.  
  
 `dwKeySize`  
 진행 요청 된 키 크기 (비트)입니다.  
  
 `ppbKeyBlob`  
 제한이 반환 된 공개/개인 키 쌍입니다.  
  
 `pcbKeyBlob`  
 제한이 `ppbKeyBlob`의 크기 (바이트)입니다.  
  
## <a name="return-value"></a>반환 값  
 성공적으로 완료 되 면 `true` 합니다. 그렇지 않으면 `false`합니다.  
  
## <a name="remarks"></a>주의  
 .NET Framework 버전 1.0 및 1.1에는 강력한 이름의 어셈블리에 서명 하는 데 1024 비트의 `dwKeySize` 필요 합니다. 버전 2.0에는 2048 비트 키에 대 한 지원 기능이 추가 되었습니다.  
  
 키를 검색 한 후에는 [StrongNameFreeBuffer](strongnamefreebuffer-function.md) 함수를 호출 하 여 할당 된 메모리를 해제 해야 합니다.  
  
 `StrongNameKeyGenEx` 함수가 성공적으로 완료 되지 않으면 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 함수를 호출하여 마지막으로 생성된 오류를 검색합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** StrongName  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [StrongNameKeyGenEx 메서드](../hosting/iclrstrongname-strongnamekeygenex-method.md)
- [StrongNameKeyGen 메서드](../hosting/iclrstrongname-strongnamekeygen-method.md)
- [ICLRStrongName 인터페이스](../hosting/iclrstrongname-interface.md)
