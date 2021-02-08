---
description: '자세히 알아보기: ICLRStrongName:: StrongNameCompareAssemblies 메서드'
title: ICLRStrongName::StrongNameCompareAssemblies 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameCompareAssemblies
helpviewer_keywords:
- ICLRStrongName::StrongNameCompareAssemblies method [.NET Framework hosting]
- StrongNameCompareAssemblies method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: b1fb356c-72cf-4aa4-8376-f291a6d97c01
topic_type:
- apiref
ms.openlocfilehash: ab02312073f9caf5059ecf7b4eeddaef864bd7b6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799653"
---
# <a name="iclrstrongnamestrongnamecompareassemblies-method"></a>ICLRStrongName::StrongNameCompareAssemblies 메서드

두 어셈블리가 강력한 이름 서명에 의해서만 다른지 여부를 결정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `wszAssembly1`  
 진행 첫 번째 어셈블리의 경로입니다.  
  
 `wszAssembly2`  
 진행 두 번째 어셈블리에 대 한 경로입니다.  
  
 `pdwResult`  
 제한이 다음 값 중 하나입니다.  
  
- `SN_CMP_DIFFERENT` (0)-어셈블리가 다른 데이터를 포함 하도록 지정 합니다.  
  
- `SN_CMP_IDENTICAL` (1)-시그니처와 체크섬을 포함 하 여 어셈블리가 정확히 동일 하도록 지정 합니다.  
  
- `SN_CMP_SIGONLY` (2)-어셈블리가 시그니처와 체크섬만 다른 것으로 지정 합니다.  
  
## <a name="return-value"></a>Return Value  

 `S_OK` 메서드가 성공적으로 완료 되었으면이 고, 그렇지 않으면입니다. 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](/windows/win32/seccrypto/common-hresult-values) 참조).  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MetaHost  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="remarks"></a>설명  

 어셈블리의 강력한 이름 서명은 어셈블리의 텍스트 이름, 버전, 문화권 및 공개 키 토큰으로 구성 됩니다.  
  
## <a name="see-also"></a>참조

- [ICLRStrongName 인터페이스](iclrstrongname-interface.md)
