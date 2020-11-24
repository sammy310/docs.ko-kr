---
title: ICLRStrongName::StrongNameTokenFromAssembly 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameTokenFromAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromAssembly
helpviewer_keywords:
- ICLRStrongName::StrongNameTokenFromAssembly method [.NET Framework hosting]
- StrongNameTokenFromAssembly method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: fc725afb-b66b-4015-aa44-1c0d1304197f
topic_type:
- apiref
ms.openlocfilehash: 90a7e60e35e1fc555681102ffa62967eb5ac01fc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671540"
---
# <a name="iclrstrongnamestrongnametokenfromassembly-method"></a>ICLRStrongName::StrongNameTokenFromAssembly 메서드

지정된 어셈블리 파일에서 강력한 이름 토큰을 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `wszFilePath`  
 진행 어셈블리에 대 한 PE (이식 가능한 실행) 파일의 경로입니다.  
  
 `ppbStrongNameToken`  
 제한이 반환 된 강력한 이름 토큰입니다.  
  
 `pcbStrongNameToken`  
 제한이 강력한 이름 토큰의 크기 (바이트)입니다.  
  
## <a name="return-value"></a>반환 값  

 `S_OK` 메서드가 성공적으로 완료 되었으면이 고, 그렇지 않으면입니다. 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](/windows/win32/seccrypto/common-hresult-values) 참조).  
  
## <a name="remarks"></a>설명  

 강력한 이름 토큰은 공개 키의 축약 된 형태입니다. 토큰은 어셈블리에 서명 하는 데 사용 되는 공개 키에서 만든 64 비트 해시입니다. 토큰은 어셈블리에 대 한 강력한 이름의 일부 이며 어셈블리 메타 데이터에서 읽을 수 있습니다.  
  
 토큰을 만든 후에는 [ICLRStrongName:: StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) 메서드를 호출 하 여 할당 된 메모리를 해제 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MetaHost  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참조

- [StrongNameTokenFromAssemblyEx 메서드](iclrstrongname-strongnametokenfromassemblyex-method.md)
- [ICLRStrongName 인터페이스](iclrstrongname-interface.md)
