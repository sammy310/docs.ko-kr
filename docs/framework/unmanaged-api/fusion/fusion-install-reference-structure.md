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
ms.openlocfilehash: 3859752fd92a76f3fef1ceced0e792109b65106a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108287"
---
# <a name="fusion_install_reference-structure"></a>FUSION_INSTALL_REFERENCE 구조체
응용 프로그램이 전역 어셈블리 캐시에 설치 된 어셈블리에 대해 수행 하는 참조를 나타냅니다.  
  
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
|`cbSize`|구조체의 크기 (바이트)입니다.|  
|`dwFlags`|향후 확장성을 위해 예약 되었습니다. 이 값은 0 이어야 합니다.|  
|`guidScheme`|참조를 추가 하는 엔터티입니다. 이 필드에는 다음 값 중 하나를 사용할 수 있습니다.<br /><br /> -FUSION_REFCOUNT_MSI_GUID: Microsoft Windows Installer을 사용 하 여 설치 된 응용 프로그램에서 어셈블리를 참조 합니다. `szIdentifier` 필드가 `MSI`로 설정 되 고 `szNonCanonicalData` 필드가 `Windows Installer`로 설정 됩니다. 이 체계는 Windows side-by-side 어셈블리에 사용 됩니다.<br />-FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: 어셈블리는 **프로그램 추가/제거** 인터페이스에 표시 되는 응용 프로그램에서 참조 됩니다. `szIdentifier` 필드는 프로그램 **추가/제거** 인터페이스를 사용 하 여 응용 프로그램을 등록 하는 토큰을 제공 합니다.<br />-FUSION_REFCOUNT_FILEPATH_GUID: 파일 시스템에서 파일이 나타내는 응용 프로그램에서 어셈블리를 참조 합니다. `szIdentifier` 필드는이 파일에 대 한 경로를 제공 합니다.<br />-FUSION_REFCOUNT_OPAQUE_STRING_GUID: 불투명 문자열만 표시 하는 응용 프로그램에서 어셈블리를 참조 합니다. `szIdentifier` 필드는이 불투명 문자열을 제공 합니다. 이 값을 제거 하면 전역 어셈블리 캐시에서 불투명 참조가 있는지 확인 하지 않습니다.<br />-FUSION_REFCOUNT_OSINSTALL_GUID:이 값은 예약 되어 있습니다.|  
|`szIdentifier`|전역 어셈블리 캐시에 어셈블리를 설치한 응용 프로그램을 식별 하는 고유한 문자열입니다. 해당 값은 `guidScheme` 필드의 값에 따라 달라 집니다.|  
|`szNonCanonicalData`|참조를 추가 하는 엔터티에서 인식할 수 있는 문자열입니다. 전역 어셈블리 캐시는이 문자열을 저장 하지만 사용 하지는 않습니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Fusion. h  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [Fusion 구조체](fusion-structures.md)
- [전역 어셈블리 캐시](../../app-domains/gac.md)
