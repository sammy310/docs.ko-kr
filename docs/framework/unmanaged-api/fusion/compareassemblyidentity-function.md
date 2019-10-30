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
ms.openlocfilehash: f6711902fb9d5c5c16084057b731746843cf0230
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108917"
---
# <a name="compareassemblyidentity-function"></a>CompareAssemblyIdentity 함수
두 어셈블리 id를 비교 하 여 같은지 여부를 확인 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
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
 진행 비교할 첫 번째 어셈블리의 텍스트 id입니다.  
  
 `fUnified1`  
 진행 `pwzAssemblyIdentity1`에 대 한 사용자 지정 통합을 나타내는 부울 플래그입니다.  
  
 `pwzAssemblyIdentity2`  
 진행 비교 하는 두 번째 어셈블리의 텍스트 id입니다.  
  
 `fUnified2`  
 진행 `pwzAssemblyIdentity2`에 대 한 사용자 지정 통합을 나타내는 부울 플래그입니다.  
  
 `pfEquivalent`  
 제한이 두 어셈블리가 동일한 지 여부를 나타내는 부울 플래그입니다.  
  
 `pResult`  
 제한이 비교에 대 한 자세한 정보를 포함 하는 [AssemblyComparisonResult](assemblycomparisonresult-enumeration.md) 열거형입니다.  
  
## <a name="return-value"></a>반환 값  
 `pfEquivalent`는 두 어셈블리가 동일한 지 여부를 나타내는 부울 값을 반환 합니다. `pResult`은 `AssemblyComparisonResult` 값 중 하나를 반환 하 여 `pfEquivalent`값에 대 한 보다 자세한 원인을 제공 합니다.  
  
## <a name="remarks"></a>주의  
 `CompareAssemblyIdentity` `pwzAssemblyIdentity1` 및 `pwzAssemblyIdentity2` 같은지 여부를 확인 합니다. `pfEquivalent`는 다음 조건 중 하나 이상에서 `true`로 설정 됩니다.  
  
- 두 어셈블리 id는 동일 합니다. 강력한 이름의 어셈블리의 경우에는 어셈블리 이름, 버전, 공개 키 토큰 및 문화권이 동일 해야 합니다. 단순한 이름의 어셈블리의 경우에는 어셈블리 이름 및 문화권과 일치 해야 합니다.  
  
- 두 어셈블리 id는 모두 .NET Framework에서 실행 되는 어셈블리를 참조 합니다. 이 조건은 어셈블리 버전 번호가 일치 하지 않는 경우에도 `true`을 반환 합니다.  
  
- 두 어셈블리는 관리 되는 어셈블리가 아니지만 `fUnified1` 또는 `fUnified2`는 `true`으로 설정 되었습니다.  
  
 `fUnified` 플래그는 강력한 이름의 어셈블리에 대 한 버전 번호 까지의 모든 버전 번호가 강력한 이름의 어셈블리와 동일한 것으로 간주 됨을 나타냅니다. 예를 들어 `pwzAssemblyIndentity1`의 값이 "MyAssembly, version = 3.0.0.0, culture = 중립, publicKeyToken = ..."이 고 `fUnified1` 값이 `true`경우이는 version 0.0.0.0에서 3.0.0.0 모든 버전의 MyAssembly를로 처리 해야 함을 나타냅니다. 상응. 이 경우 `pwzAssemblyIndentity2`가 `pwzAssemblyIndentity1`와 동일한 어셈블리를 참조 하는 경우에는 더 낮은 버전 번호가 있다는 점을 제외 하 고 `pfEquivalent`는 `true`로 설정 됩니다. `pwzAssemblyIdentity2`에서 더 높은 버전 번호를 참조 하는 경우 `fUnified2`의 값이 `true`인 경우에만 `pfEquivalent`를 `true`으로 설정 합니다.  
  
 `pResult` 매개 변수는 두 어셈블리가 동일 하거나 동일 하지 않은 것으로 간주 되는 이유에 대 한 특정 정보를 포함 합니다. 자세한 내용은 [AssemblyComparisonResult 열거형](assemblycomparisonresult-enumeration.md)을 참조 하세요.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Fusion. h  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [Fusion 전역 정적 함수](fusion-global-static-functions.md)
- [AssemblyComparisonResult 열거형](assemblycomparisonresult-enumeration.md)
