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
ms.openlocfilehash: adde52dddb63b83dcd7ff10703a43928d9601c92
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140626"
---
# <a name="strongnamecompareassemblies-function"></a>StrongNameCompareAssemblies 함수
두 어셈블리가 강력한 이름 서명에 의해서만 다른지 여부를 결정합니다.  
  
 이 함수는 더 이상 사용 되지 않습니다. 대신 [ICLRStrongName:: StrongNameCompareAssemblies](../hosting/iclrstrongname-strongnamecompareassemblies-method.md) 메서드를 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
BOOLEAN StrongNameCompareAssemblies (  
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
  
## <a name="return-value"></a>반환 값  
 성공적으로 완료 되 면 `true` 합니다. 그렇지 않으면 `false`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** StrongName  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="remarks"></a>주의  
 어셈블리의 강력한 이름 서명은 어셈블리의 텍스트 이름, 버전, 문화권 및 공개 키 토큰으로 구성 됩니다.  
  
 `StrongNameCompareAssemblies` 함수가 성공적으로 완료 되지 않으면 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 함수를 호출하여 마지막으로 생성된 오류를 검색합니다.  
  
## <a name="see-also"></a>참조

- [StrongNameCompareAssemblies 메서드](../hosting/iclrstrongname-strongnamecompareassemblies-method.md)
- [ICLRStrongName 인터페이스](../hosting/iclrstrongname-interface.md)
