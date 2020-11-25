---
title: StrongNameHashSize 함수
ms.date: 03/30/2017
api_name:
- StrongNameHashSize
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameHashSize
helpviewer_keywords:
- StrongNameHashSize function [.NET Framework strong naming]
ms.assetid: 738c98d7-a60c-45fe-a296-220af05e6991
topic_type:
- apiref
ms.openlocfilehash: 1116fcde754f966a783f4fdca85df8bd3ca1b0ba
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724431"
---
# <a name="strongnamehashsize-function"></a>StrongNameHashSize 함수

지정된 해시 알고리즘을 사용하여 해시에 필요한 버퍼 크기를 가져옵니다.  
  
 이 함수는 더 이상 사용 되지 않습니다. 대신 [ICLRStrongName:: StrongNameHashSize](../hosting/iclrstrongname-strongnamehashsize-method.md) 메서드를 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
BOOLEAN StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `ulHashAlg`  
 진행 버퍼 크기를 계산 하는 데 사용 되는 해시 알고리즘입니다.  
  
 `pcbSize`  
 제한이 반환 된 버퍼 크기 (바이트)입니다.  
  
## <a name="return-value"></a>반환 값  

 `true` 성공적으로 완료 되 면 그렇지 않으면 `false` 입니다.  
  
## <a name="remarks"></a>설명  

 `StrongNameHashSize`함수가 성공적으로 완료되지 않으면 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 함수를 호출하여 마지막으로 생성된 오류를 검색합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** StrongName  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [StrongNameHashSize 메서드](../hosting/iclrstrongname-strongnamehashsize-method.md)
- [ICLRStrongName 인터페이스](../hosting/iclrstrongname-interface.md)
