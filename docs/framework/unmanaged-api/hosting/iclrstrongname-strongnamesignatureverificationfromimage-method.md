---
title: ICLRStrongName::StrongNameSignatureVerificationFromImage 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureVerificationFromImage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerificationFromImage
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureVerificationFromImage method [.NET Framework hosting]
- StrongNameSignatureVerificationFromImage method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: da91c138-ee30-4fd4-a040-464d97d7e41a
topic_type:
- apiref
ms.openlocfilehash: 1ba7355fae1888436d57562cc21d3865ebc7a4f4
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/21/2020
ms.locfileid: "83763178"
---
# <a name="iclrstrongnamestrongnamesignatureverificationfromimage-method"></a>ICLRStrongName::StrongNameSignatureVerificationFromImage 메서드
메모리에 이미 매핑된 어셈블리가 연결된 공개 키에 유효한지 확인합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pbBase`  
 진행 매핑된 어셈블리 매니페스트의 상대 가상 주소입니다.  
  
 `dwLength`  
 진행 매핑된 이미지의 크기 (바이트)입니다.  
  
 `dwInFlags`  
 진행 확인 동작에 영향을 주는 플래그입니다. 다음 값이 지원 됩니다.  
  
- `SN_INFLAG_FORCE_VER`(0x00000001)-레지스트리 설정을 재정의 해야 하는 경우에도 강제로 확인 합니다.  
  
- `SN_INFLAG_INSTALL`(0x00000002)-이 이미지에서 수행 되는 첫 번째 확인을 지정 합니다.  
  
- `SN_INFLAG_ADMIN_ACCESS`(0x00000004)-캐시가 관리 권한이 있는 사용자 에게만 액세스를 허용 하도록 지정 합니다.  
  
- `SN_INFLAG_USER_ACCESS`(0x00000008)-현재 사용자만 어셈블리에 액세스할 수 있도록 지정 합니다.  
  
- `SN_INFLAG_ALL_ACCESS`(0x00000010)-캐시가 액세스 제한에 대 한 보장을 제공 하지 않도록 지정 합니다.  
  
- `SN_INFLAG_RUNTIME`(0x80000000)-내부 디버깅용으로 예약 되어 있습니다.  
  
 `pdwOutFlags`  
 제한이 추가 출력 정보에 대 한 플래그입니다. 지원 되는 값은 다음과 같습니다.  
  
- `SN_OUTFLAG_WAS_VERIFIED`(0x00000001)-이 값은 `false` 레지스트리 설정으로 인해 확인이 성공 하도록 지정 하기 위해로 설정 됩니다.  
  
## <a name="return-value"></a>Return Value  
 `S_OK`메서드가 성공적으로 완료 되었으면이 고, 그렇지 않으면입니다. 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](/windows/win32/seccrypto/common-hresult-values) 참조).  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MetaHost  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRStrongName 인터페이스](iclrstrongname-interface.md)
