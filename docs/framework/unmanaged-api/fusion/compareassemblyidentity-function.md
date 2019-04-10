---
title: CompareAssemblyIdentity 함수
ms.date: 03/30/2017
api_name:
- CompareAssemblyIdentity
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- CompareAssemblyIdentity
helpviewer_keywords:
- CompareAssemblyIdentity function [.NET Framework fusion]
ms.assetid: 8b364ae1-8efa-4744-a7da-81fd093d84d6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 652000367c19572f73296c704047830ce1c74574
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59231047"
---
# <a name="compareassemblyidentity-function"></a>CompareAssemblyIdentity 함수
동일한 지 여부를 확인 하려면 두 개의 어셈블리 id를 비교 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDAPI CompareAssemblyIdentity (  
    [in]  LPCWSTR                  pwzAssemblyIdentity1,  
    [in]  BOOL                     fUnified1,  
    [in]  LPCWSTR                  pwzAssemblyIdentity2,  
    [in]  BOOL                     fUnified2,  
    [out] BOOL                     *pfEquivalent,  
    [out] AssemblyComparisonResult *pResult  
 );  
```  
  
## <a name="parameters"></a>매개 변수  
 `pwzAssemblyIdentity1`  
 [in] 텍스트 비교에 첫 번째 어셈블리의 id입니다.  
  
 `fUnified1`  
 [in] 에 대 한 사용자 지정 통합을 나타내는 부울 플래그 `pwzAssemblyIdentity1`합니다.  
  
 `pwzAssemblyIdentity2`  
 [in] 비교할에서 두 번째 어셈블리의 텍스트 id입니다.  
  
 `fUnified2`  
 [in] 에 대 한 사용자 지정 통합을 나타내는 부울 플래그 `pwzAssemblyIdentity2`합니다.  
  
 `pfEquivalent`  
 [out] 두 어셈블리 같은지 여부를 나타내는 부울 플래그입니다.  
  
 `pResult`  
 [out] [AssemblyComparisonResult](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md) 비교에 대 한 자세한 정보를 포함 하는 열거형입니다.  
  
## <a name="return-value"></a>반환 값  
 `pfEquivalent` 두 어셈블리 같은지 여부를 나타내는 부울 값을 반환 합니다. `pResult` 중 하나를 반환 합니다 `AssemblyComparisonResult` 값을 값에 대 한 자세한 이유를 제공 `pfEquivalent`합니다.  
  
## <a name="remarks"></a>설명  
 `CompareAssemblyIdentity` 확인 여부 `pwzAssemblyIdentity1` 및 `pwzAssemblyIdentity2` 동일 합니다. `pfEquivalent` 로 설정 된 `true` 다음 조건 중 하나 이상:  
  
-   두 어셈블리 id는 동일 합니다. 강력한 이름의 어셈블리 어셈블리일 어셈블리 이름, 버전, 공개 키 토큰 및 문화권 동일 하 게 됩니다. 단순한 이름의 어셈블리에 대 한 어셈블리일 경우 어셈블리 이름 및 문화권입니다.  
  
-   두 어셈블리 id는.NET Framework에서 실행 되는 어셈블리를 참조 하십시오. 이 반환 `true` 어셈블리 버전 번호가 일치 하지 않는 경우에 합니다.  
  
-   두 어셈블리는 관리 되는 어셈블리 하지만 `fUnified1` 나 `fUnified2` 로 설정 된 `true`합니다.  
  
 `fUnified` 플래그는 강력한 이름의 어셈블리의 버전 번호까지 모든 버전 번호가 동일 하다 고 간주 강력한 이름의 어셈블리를 나타냅니다. 예를 들어 경우 값 `pwzAssemblyIndentity1` 가 "MyAssembly, 버전 3.0.0.0, culture = neutral, publicKeyToken = =...", 값 `fUnified1` 는 `true`, 모든 버전의 MyAssembly 버전 3.0.0.0에 0.0.0.0 함을 나타냅니다 동등한 것으로 처리 합니다. 이러한 경우의 경우 `pwzAssemblyIndentity2` 와 동일한 어셈블리를 가리킵니다 `pwzAssemblyIndentity1`낮은 버전 번호에 있는 점을 제외 하 고, `pfEquivalent` 로 설정 되어 `true`합니다. 하는 경우 `pwzAssemblyIdentity2` 더 높은 버전 번호를 가리킵니다 `pfEquivalent` 로 설정 된 `true` 경우에만 값 `fUnified2` 는 `true`합니다.  
  
 `pResult` 이유 두 어셈블리 것으로 간주 됩니다 동등 하거나 해당 하는 방법에 대 한 특정 정보를 포함 하는 매개 변수입니다. 자세한 내용은 [AssemblyComparisonResult 열거형](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** Fusion.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [Fusion 전역 정적 함수](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
- [AssemblyComparisonResult 열거형](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md)
