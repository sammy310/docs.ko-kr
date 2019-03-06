---
title: StrongNameCompareAssemblies 함수
ms.date: 03/30/2017
api_name:
- StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameCompareAssemblies
helpviewer_keywords:
- StrongNameCompareAssemblies function [.NET Framework strong naming]
ms.assetid: 763f2375-efc6-4219-8806-a3b0567ef72b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dd3813d977f94db4168da8c888485b323f4072ad
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471279"
---
# <a name="strongnamecompareassemblies-function"></a>StrongNameCompareAssemblies 함수
두 어셈블리가 강력한 이름 서명에 의해서만 다른지 여부를 결정합니다.  
  
 이 함수는 더 이상 사용 되지 않습니다. 사용 된 [iclrstrongname:: Strongnamecompareassemblies](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md) 메서드 대신 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
BOOLEAN StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `wszAssembly1`  
 [in] 첫 번째 어셈블리에 대 한 경로입니다.  
  
 `wszAssembly2`  
 [in] 두 번째 어셈블리에 대 한 경로입니다.  
  
 `pdwResult`  
 [out] 다음 값 중 하나입니다.  
  
-   `SN_CMP_DIFFERENT` (0)-어셈블리에 다른 데이터가 포함 되어 있는지를 지정 합니다.  
  
-   `SN_CMP_IDENTICAL` (1)-어셈블리가 정확히 동일한 지, 해당 서명과 체크섬을 포함 하 여 지정 합니다.  
  
-   `SN_CMP_SIGONLY` (2)-는 어셈블리를 서명 및 체크섬에 의해서만 달라 지는 것을 지정 합니다.  
  
## <a name="return-value"></a>반환 값  
 `true` 성공적으로 완료 됩니다. 그렇지 않으면 `false`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** StrongName.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="remarks"></a>설명  
 어셈블리의 강력한 이름 시그니처는 어셈블리의 텍스트 이름, 버전, 문화권 및 공개 키 토큰으로 구성 됩니다.  
  
 경우는 `StrongNameCompareAssemblies` 함수가 성공적으로 완료으로 호출 되지 않으면 합니다 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) 마지막 생성 된 오류를 검색 하는 함수입니다.  
  
## <a name="see-also"></a>참고자료
- [StrongNameCompareAssemblies 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamecompareassemblies-method.md)
- [ICLRStrongName 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
