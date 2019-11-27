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
ms.openlocfilehash: f3bb978b8358992fd9aa7da922e28efc1ed1a951
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446487"
---
# <a name="emitmanifest-method"></a>EmitManifest 메서드
최종 매니페스트를 내보냅니다. 다른 모든 파일을 가져온 후이 메서드를 호출 하 고 모든 옵션을 설정 합니다. 바인딩되지 않은 모듈에 대해이 메서드를 호출 하지 마십시오.  
  
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
 [StrongNameSignatureSize 함수](../strong-naming/strongnamesignaturesize-function.md)에서 검색 된 어셈블리 파일에서 예약할 크기를 수신 합니다.  
  
 `ptkManifest`  
 선택적으로 어셈블리 매니페스트 토큰을 받습니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 S_OK을 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 Alink가 필요 합니다.  
  
## <a name="see-also"></a>참고자료

- [IALink 인터페이스](ialink-interface.md)
- [IALink2 인터페이스](ialink2-interface.md)
- [ALink API](index.md)
