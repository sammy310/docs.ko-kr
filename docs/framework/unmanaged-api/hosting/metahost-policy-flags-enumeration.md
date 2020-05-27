---
title: METAHOST_POLICY_FLAGS 열거형
ms.date: 03/30/2017
api_name:
- METAHOST_POLICY_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- METAHOST_POLICY_FLAGS
helpviewer_keywords:
- METAHOST_POLICY_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 3bb4b526-0118-42e2-ba59-c95648528ce9
topic_type:
- apiref
ms.openlocfilehash: bb40ed65a2e34f1bf293e4c4c842d7db63d2eaa5
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008445"
---
# <a name="metahost_policy_flags-enumeration"></a>METAHOST_POLICY_FLAGS 열거형
대부분의 런타임 호스트에 공통 되는 바인딩 정책을 제공 합니다. 이 열거형은 [ICLRMetaHostPolicy:: GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) 메서드에서 사용 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum {  
    METAHOST_POLICY_HIGHCOMPAT              = 0x00,  
    METAHOST_POLICY_APPLY_UPGRADE_POLICY    = 0x08,  
    METAHOST_POLICY_EMULATE_EXE_LAUNCH      = 0x10,  
    METAHOST_POLICY_SHOW_ERROR_DIALOG       = 0x20,  
    METAHOST_POLICY_USE_PROCESS_IMAGE_PATH  = 0x40,  
    METAHOST_POLICY_ENSURE_SKU_SUPPORTED    = 0x80,  
    METAHOST_POLICY_IGNORE_ERROR_MODE       = 0x1000  
  
} METAHOST_POLICY_FLAGS;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`METAHOST_POLICY_HIGHCOMPAT`|현재 프로세스에 로드 되는 CLR (공용 언어 런타임)을 고려 하지 않는 높은 호환성 정책을 정의 합니다. 대신 어셈블리 파일 자체, 선언 된 기본 제공 버전 또는 구성 파일에서 파생 된 구성 요소의 설치 된 Clr 및 기본 설정만 고려 합니다.|  
|`METAHOST_POLICY_APPLY_UPGRADE_POLICY`|HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft의 내용에 따라 정확히 일치 하는 항목을 찾을 수 없는 경우 버전 바인드 결과에 업그레이드 정책을 적용 \\ 합니다. NETFramework\Policy\Upgrades. [RUNTIME_INFO_UPGRADE_VERSION](runtime-info-flags-enumeration.md)와 동일한 효과가 있습니다.|  
|`METAHOST_POLICY_EMULATE_EXE_LAUNCH`|호출에 제공 된 이미지가 새 프로세스에서 시작 된 것 처럼 바인딩 결과가 반환 됩니다. 현재는 `GetRequestedRuntime` 설치 된 런타임 집합에 대해 로드 가능한 런타임 집합과 바인딩 집합을 무시 합니다. 이 플래그를 사용 하면 호스트에서 실행 될 때 EXE가 바인딩될 런타임을 결정할 수 있습니다.|  
|`METAHOST_POLICY_SHOW_ERROR_DIALOG`|에서 `GetRequestedRuntime` 입력 매개 변수와 호환 되는 런타임을 찾을 수 없는 경우 오류 대화 상자가 표시 됩니다. .NET Framework 4.5부터이 오류 대화 상자는 사용자가 적절 한 기능을 사용 하도록 설정할지 여부를 묻는 Windows 기능 대화 상자의 형식을 사용할 수 있습니다.|  
|`METAHOST_POLICY_USE_PROCESS_IMAGE_PATH`|`GetRequestedRuntime`는 프로세스 이미지 (및 해당 구성 파일)를 바인딩 프로세스에 대 한 추가 입력으로 사용 합니다. 기본적으로는 `GetRequestedRuntime` 바인딩할 런타임을 결정할 때 프로세스 이미지 경로 (일반적으로 프로세스를 시작 하는 데 사용 된 EXE)로 대체 되지 않습니다.|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|`GetRequestedRuntime`구성 파일에 사용할 수 있는 정보가 없을 때 적절 한 SKU가 설치 되어 있는지 확인 해야 합니다. 이렇게 하면 구성 파일이 없는 응용 프로그램이 .NET Framework의 기본 설치 보다 더 작은 Sku에서 정상적으로 장애 조치할 수 있습니다. 기본적으로에서는 `GetRequestedRuntime` 구성 파일 요소에 sku 특성이 지정 되지 않은 경우 적절 한 SKU가 설치 되어 있는지 여부를 확인 하지 않습니다 `<supportedRuntime />` .|  
|`METAHOST_POLICY_IGNORE_ERROR_MODE`|`GetRequestedRuntime`[SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) 함수를 호출 하 여 설정 된 SEM_FAILCRITICALERRORS를 무시 하 고 오류 대화 상자를 표시 해야 합니다. 기본적으로 SEM_FAILCRITICALERRORS는 오류 대화 상자를 표시 하지 않습니다. 다른 프로세스에서 상속 되었을 수 있으며, 시나리오에서 자동 오류가 바람직하지 않을 수 있습니다.|  
  
## <a name="remarks"></a>설명  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Metahost  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [호스팅 열거형](hosting-enumerations.md)
- [GetRequestedRuntime 메서드](iclrmetahostpolicy-getrequestedruntime-method.md)
