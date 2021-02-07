---
description: '자세히 알아보기: StrongNameKeyGenEx 함수'
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
ms.openlocfilehash: b6c103d16cac1b4668e4b478a0947970b5b44a0b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99686819"
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
 진행 요청 된 키 컨테이너 이름입니다. `wszKeyContainer` 임시 이름을 생성 하려면 비어 있지 않은 문자열 이거나 null 이어야 합니다.  
  
 `dwFlags`  
 진행 키를 등록 된 상태로 유지할지 여부를 지정 합니다. 지원되는 값은 다음과 같습니다.  
  
- 0x00000000- `wszKeyContainer` 임시 키 컨테이너 이름을 생성 하기 위해가 null 일 때 사용 됩니다.  
  
- 0x00000001 ( `SN_LEAVE_KEY` )-키를 등록 된 상태로 유지 하도록 지정 합니다.  
  
 `dwKeySize`  
 진행 요청 된 키 크기 (비트)입니다.  
  
 `ppbKeyBlob`  
 제한이 반환 된 공개/개인 키 쌍입니다.  
  
 `pcbKeyBlob`  
 제한이 의 크기 (바이트)입니다 `ppbKeyBlob` .  
  
## <a name="return-value"></a>Return Value  

 `true` 성공적으로 완료 되 면 그렇지 않으면 `false` 입니다.  
  
## <a name="remarks"></a>설명  

 .NET Framework 버전 1.0 및 1.1에는 `dwKeySize` 강력한 이름으로 어셈블리에 서명 하는 데 1024 비트가 필요 합니다. 버전 2.0은 2048 비트 키에 대 한 지원 기능을 추가 합니다.  
  
 키를 검색 한 후에는 [StrongNameFreeBuffer](strongnamefreebuffer-function.md) 함수를 호출 하 여 할당 된 메모리를 해제 해야 합니다.  
  
 `StrongNameKeyGenEx`함수가 성공적으로 완료되지 않으면 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 함수를 호출하여 마지막으로 생성된 오류를 검색합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** StrongName  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [StrongNameKeyGenEx 메서드](../hosting/iclrstrongname-strongnamekeygenex-method.md)
- [StrongNameKeyGen 메서드](../hosting/iclrstrongname-strongnamekeygen-method.md)
- [ICLRStrongName 인터페이스](../hosting/iclrstrongname-interface.md)
