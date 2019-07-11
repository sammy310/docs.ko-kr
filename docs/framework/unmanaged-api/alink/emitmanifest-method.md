---
title: EmitManifest 메서드
ms.date: 03/30/2017
api_name:
- EmitManifest
- IALink.EmitManifest
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitManifest
helpviewer_keywords:
- EmitManifest method
ms.assetid: fdebc1f3-b62e-4d9e-b775-8ccaa8ecb250
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 91dc4cb7d64d49d1e95c0c8eb79a29736559d842
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742088"
---
# <a name="emitmanifest-method"></a>EmitManifest 메서드
최종 매니페스트를 내보냅니다. 기타 모든 파일을 가져오는 모든 옵션을 설정한 후이 메서드를 호출 합니다. 바인딩되지 않은 모듈에 대 한이 메서드를 호출 하지 마세요.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EmitManifest(  
    mdAssembly   AssemblyID,  
    DWORD*       pdwReserveSize,  
    mdAssembly*  ptkManifest  
) PURE;  
```  
  
## <a name="parameters"></a>매개 변수  
 `AssemblyID`  
 어셈블리의 ID입니다.  
  
 `pdwReserveSize`  
 검색 된 어셈블리 파일에서 예약 크기를 받는 [StrongNameSignatureSize 함수](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md)합니다.  
  
 `ptkManifest`  
 필요에 따라 어셈블리 매니페스트 토큰을 받습니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 Alink.h가 필요합니다.  
  
## <a name="see-also"></a>참고자료

- [IALink 인터페이스](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [IALink2 인터페이스](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [ALink API](../../../../docs/framework/unmanaged-api/alink/index.md)
