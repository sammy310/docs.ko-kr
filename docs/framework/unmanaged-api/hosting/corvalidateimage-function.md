---
title: _CorValidateImage 함수
ms.date: 03/30/2017
api_name:
- _CorValidateImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorValidateImage
helpviewer_keywords:
- _CorValidateImage function [.NET Framework hosting]
ms.assetid: 0117e080-05f9-4772-885d-e1847230947c
topic_type:
- apiref
ms.openlocfilehash: 3a6da0e845fa50d090cdf0808b211a5806c40961
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178212"
---
# <a name="_corvalidateimage-function"></a>_CorValidateImage 함수
관리되는 모듈 이미지의 유효성을 검사하고 로드후 운영 체제 로더에 통보합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
STDAPI _CorValidateImage (
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `ImageBase`  
 【인】 관리 코드로 유효성을 검사하는 이미지의 시작 위치에 대한 포인터입니다. 이미지가 이미 메모리에 로드되어야 합니다.  
  
 `FileName`  
 【인】 이미지의 파일 이름입니다.  
  
## <a name="return-value"></a>Return Value  
 이 함수는 다음 `E_INVALIDARG` `E_OUTOFMEMORY`값뿐만 아니라 표준 값 , 및 `E_UNEXPECTED` `E_FAIL`및 을 반환합니다.  
  
|반환 값|Description|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|이미지가 잘못되었습니다. 이 값은 HRESULT 0xC000007BL입니다.|  
|`STATUS_SUCCESS`|이미지가 유효합니다. 이 값은 HRESULT 0x00000000L입니다.|  
  
## <a name="remarks"></a>설명  
 Windows XP 및 이후 버전에서 운영 체제 로더는 COFF(공통 개체 파일 형식) 헤더의 COM 설명자 디렉토리 비트를 검사하여 관리되는 모듈을 확인합니다. 설정된 비트는 관리되는 모듈을 나타냅니다. 로더가 관리되는 모듈을 감지하면 MsCorEE.dll을 `_CorValidateImage`로드하고 다음 작업을 수행하는 호출을 수행합니다.  
  
- 이미지가 유효한 관리 모듈임을 확인합니다.  
  
- 이미지의 진입점을 공통 언어 런타임(CLR)의 진입점으로 변경합니다.  
  
- 64비트 버전의 Windows의 경우 메모리에 있는 이미지를 PE32에서 PE32+ 형식으로 변환하여 수정합니다.  
  
- 관리되는 모듈 이미지가 로드되면 로더로 돌아갑니다.  
  
 실행 가능한 이미지의 경우 운영 체제 로더는 실행 _CorExeMain 에 지정된 진입점에 관계없이 [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) 함수를 호출합니다. DLL 어셈블리 이미지의 경우 로더는 [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) 함수를 호출합니다.  
  
 `_CorExeMain`또는 `_CorDllMain` 다음 작업을 수행합니다.  
  
- CLR을 초기화합니다.  
  
- 어셈블리의 CLR 헤더에서 관리되는 진입점을 찾습니다.  
  
- 실행을 시작합니다.  
  
 로더는 관리되는 모듈 이미지가 언로드될 때 [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) 함수를 호출합니다. 그러나 이 함수는 어떠한 작업도 수행하지 않습니다. 그냥 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [메타데이터 전역 정적 함수](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
