---
title: FUSION_INSTALL_REFERENCE 구조체
ms.date: 03/30/2017
api_name:
- FUSION_INSTALL_REFERENCE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- FUSION_INSTALL_REFERENCE
helpviewer_keywords:
- FUSION_INSTALL_REFERENCE structure [.NET Framework fusion]
ms.assetid: ae181ec8-36bf-4ed1-9a02-ca27d417c80b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ec18d5d5a6574cb0e08a6c4d6eaedcbcbf6886cd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759358"
---
# <a name="fusioninstallreference-structure"></a>FUSION_INSTALL_REFERENCE 구조체
응용 프로그램에 전역 어셈블리 캐시에 설치 하는 어셈블리를 응용 프로그램에는 참조를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct _FUSION_INSTALL_REFERENCE_ {  
    DWORD    cbSize,  
    DWORD    dwFlags,  
    GUID     guidScheme,  
    LPCWSTR  szIdentifier,  
    LPCWSTR  szNonCanonicalData  
} FUSION_INSTALL_REFERENCE, *LPFUSION_INSTALL_REFERENCE;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`cbSize`|크기 (바이트)에서 구조입니다.|  
|`dwFlags`|향후 확장성을 위해 예약 되어 있습니다. 이 값은 0 (영) 여야 합니다.|  
|`guidScheme`|참조를 추가 하는 엔터티. 이 필드는 다음 값 중 하나일 수 있습니다.<br /><br /> -   FUSION_REFCOUNT_MSI_GUID: 어셈블리는 Microsoft Windows Installer를 사용 하 여 설치 된 응용 프로그램에서 참조 됩니다. `szIdentifier` 필드 설정 됩니다 `MSI`, 및 `szNonCanonicalData` 필드를로 `Windows Installer`합니다. 이 체계는 Windows side-by-side-어셈블리에 사용 됩니다.<br />-   FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: 어셈블리에 표시 되는 응용 프로그램에서 참조 되는 **프로그램 추가/제거** 인터페이스입니다. 합니다 `szIdentifier` 필드는 사용 하 여 응용 프로그램을 등록 하는 토큰을 제공 합니다 **프로그램 추가/제거** 인터페이스입니다.<br />-   FUSION_REFCOUNT_FILEPATH_GUID: 어셈블리는 파일 시스템에 파일이 표시 되는 응용 프로그램에서 참조 됩니다. `szIdentifier` 필드는이 파일의 경로를 제공 합니다.<br />-   FUSION_REFCOUNT_OPAQUE_STRING_GUID: 어셈블리는 불투명 문자열에 의해서만 표시 되는 응용 프로그램에서 참조 됩니다. `szIdentifier` 필드는이 불투명 문자열을 제공 합니다. 이 값을 제거 하면 전역 어셈블리 캐시 불투명 참조가 있는지 확인 하지 않습니다.<br />-   FUSION_REFCOUNT_OSINSTALL_GUID: 이 값은 예약 되어 있습니다.|  
|`szIdentifier`|전역 어셈블리 캐시에 어셈블리를 설치 하는 응용 프로그램을 식별 하는 고유 문자열입니다. 값에 따라 값이 달라는 `guidScheme` 필드입니다.|  
|`szNonCanonicalData`|엔터티 참조를 추가 하 여만 인식할 수는 문자열입니다. 전역 어셈블리 캐시는이 문자열을 저장 하지만 사용 하지 않습니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** Fusion.h  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [Fusion 구조체](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
- [전역 어셈블리 캐시](../../../../docs/framework/app-domains/gac.md)
