---
description: _CorValidateImage 함수에 대해 자세히 알아보세요.
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
ms.openlocfilehash: f3d91c2d7e05786f7bfb0ab94b64e2cfb84a21d3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746245"
---
# <a name="_corvalidateimage-function"></a>_CorValidateImage 함수

관리 되는 모듈 이미지의 유효성을 검사 하 고, 운영 체제 로더가 로드 된 후이를 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
STDAPI _CorValidateImage (
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `ImageBase`  
 진행 관리 코드로 유효성을 검사할 이미지의 시작 위치에 대 한 포인터입니다. 이미지가 이미 메모리에 로드 되어 있어야 합니다.  
  
 `FileName`  
 진행 이미지의 파일 이름입니다.  
  
## <a name="return-value"></a>Return Value  

 이 함수는 `E_INVALIDARG` `E_OUTOFMEMORY` `E_UNEXPECTED` 다음 값 뿐만 아니라 표준 값,, 및를 반환 합니다 `E_FAIL` .  
  
|반환 값|설명|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|이미지가 잘못 되었습니다. 이 값에는 HRESULT 0xC000007BL이 있습니다.|  
|`STATUS_SUCCESS`|이미지가 올바릅니다. 이 값에는 HRESULT 0x00000000L이 있습니다.|  
  
## <a name="remarks"></a>설명  

 Windows XP 이상 버전에서 운영 체제 로더는 COFF (common object file format) 헤더의 COM 설명자 디렉터리 비트를 검사 하 여 관리 되는 모듈을 확인 합니다. 설정 비트는 관리 되는 모듈을 나타냅니다. 로더가 관리 되는 모듈을 검색 하는 경우 MsCorEE.dll를 로드 하 고를 호출 하 여 `_CorValidateImage` 다음 작업을 수행 합니다.  
  
- 이미지가 올바른 관리 되는 모듈 인지 확인 합니다.  
  
- 이미지의 진입점을 CLR (공용 언어 런타임)의 진입점으로 변경 합니다.  
  
- 64 비트 버전의 Windows에서는 PE32에서 PE32 + 형식으로 변환 하 여 메모리에 있는 이미지를 수정 합니다.  
  
- 관리 되는 모듈 이미지가 로드 될 때 로더에 반환 됩니다.  
  
 실행 가능 이미지의 경우 운영 체제 로더에서 실행 파일에 지정 된 진입점에 관계 없이 [_CorExeMain](corexemain-function.md) 함수를 호출 합니다. DLL 어셈블리 이미지의 경우 로더는 [_CorDllMain](cordllmain-function.md) 함수를 호출 합니다.  
  
 `_CorExeMain` 또는 `_CorDllMain` 에서는 다음 작업을 수행 합니다.  
  
- CLR을 초기화 합니다.  
  
- 어셈블리의 CLR 헤더에서 관리 되는 진입점을 찾습니다.  
  
- 실행을 시작 합니다.  
  
 로더는 관리 되는 모듈 이미지가 언로드될 때 [_CorImageUnloading](corimageunloading-function.md) 함수를 호출 합니다. 그러나이 함수는 아무 작업도 수행 하지 않습니다. 만 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [메타데이터 전역 정적 함수](../metadata/metadata-global-static-functions.md)
