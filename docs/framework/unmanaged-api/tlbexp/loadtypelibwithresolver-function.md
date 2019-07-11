---
title: LoadTypeLibWithResolver 함수
ms.date: 03/30/2017
api_name:
- LoadTypeLibWithResolver
api_location:
- TlbRef.dll
api_type:
- DLLExport
f1_keywords:
- LoadTypeLibWithResolver
helpviewer_keywords:
- LoadTypeLibWithResolver function [.NET Framework]
ms.assetid: 7123a89b-eb9b-463a-a552-a081e33b0a3a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5d2f5ad2afb2e73acead82369782f142aa10aac3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782707"
---
# <a name="loadtypelibwithresolver-function"></a>LoadTypeLibWithResolver 함수
형식 라이브러리를 로드 하 고 제공 된 사용 [ITypeLibResolver 인터페이스](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) 내부적으로 참조 된 형식 라이브러리를 해결 하려면.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT LoadTypeLibWithResolver(  
    [in]  LPCOLESTR           szFile,  
    [in]  REGKIND             regkind,  
    [in]  ITypeLibResolver   *pTlbResolver,  
    [out] ITypeLib          **pptlib);  
```  
  
## <a name="parameters"></a>매개 변수  
 `szFile`  
 [in] 형식 라이브러리의 파일 경로입니다.  
  
 `regkind`  
 [in] A [REGKIND 열거형](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/ne-oleauto-tagregkind) 형식 라이브러리를 등록 하는 방법을 제어 하는 플래그입니다. 가능한 값은:  
  
- `REGKIND_DEFAULT`: 기본 등록 동작을 사용 합니다.  
  
- `REGKIND_REGISTER`: 이 형식 라이브러리를 등록 합니다.  
  
- `REGKIND_NONE`: 이 형식 라이브러리를 등록 하지 마십시오.  
  
 `pTlbResolver`  
 [in] 구현에 대 한 포인터를 [ITypeLibResolver 인터페이스](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)합니다.  
  
 `pptlib`  
 [out] 로드 되는 형식 라이브러리에 대 한 참조입니다.  
  
## <a name="return-value"></a>반환 값  
 다음 표에 나열 된 HRESULT 값 중 하나입니다.  
  
|반환 값|의미|  
|------------------|-------------|  
|`S_OK`|명령 실행 성공|  
|`E_OUTOFMEMORY`|메모리가 부족합니다.|  
|`E_POINTER`|포인터 중 하나 이상이 올바르지 않습니다.|  
|`E_INVALIDARG`|인수 중 하나 이상이 올바르지 않습니다.|  
|`TYPE_E_IOERROR`|함수는 파일에 쓰지 못했습니다.|  
|`TYPE_E_REGISTRYACCESS`|시스템 등록 데이터베이스를 열 수 없습니다.|  
|`TYPE_E_INVALIDSTATE`|형식 라이브러리를 열 수 없습니다.|  
|`TYPE_E_CANTLOADLIBRARY`|형식 라이브러리를 DLL을 로드할 수 없습니다.|  
  
## <a name="remarks"></a>설명  
 합니다 [Tlbexp.exe (형식 라이브러리 내보내기)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) 호출을 `LoadTypeLibWithResolver` 어셈블리를 형식 라이브러리로 변환 하는 동안 함수입니다.  
  
 이 함수는 레지스트리에 대 한 최소한의 액세스를 사용 하 여 지정 된 형식 라이브러리를 로드합니다. 함수는 다음 내부적으로 참조 된 형식 라이브러리를 로드 및 부모 형식 라이브러리에 추가 해야 합니다는 각각에 대 한 형식 라이브러리를 검사 합니다.  
  
 참조 된 형식 라이브러리를 로드 하기 전에 해당 참조 파일 경로 전체 파일 경로를 확인 해야 합니다. 이 통해 이루어집니다를 [ResolveTypeLib 메서드](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md) 가 제공 하는 합니다 [ITypeLibResolver 인터페이스](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)에 전달 되는 `pTlbResolver` 매개 변수입니다.  
  
 참조 된 형식 라이브러리의 전체 파일 경로, 알려진 경우는 `LoadTypeLibWithResolver` 함수 로드 하 고 결합 된 마스터 형식 라이브러리를 만들고 부모 형식 라이브러리에 참조 된 형식 라이브러리를 추가 합니다.  
  
 함수를 확인 하 고 모든 내부적으로 참조 된 형식 라이브러리를 로드 한 후 마스터 확인 된 형식 라이브러리에 대 한 참조를 반환 합니다는 `pptlib` 매개 변수입니다.  
  
 `LoadTypeLibWithResolver` 함수는 일반적으로 호출한 합니다 [Tlbexp.exe (형식 라이브러리 내보내기)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)를 제공 하는 자체 내부 [ITypeLibResolver 인터페이스](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) 구현에는 `pTlbResolver` 매개 변수입니다.  
  
 호출 하는 경우 `LoadTypeLibWithResolver` 를 직접 제공 해야 사용자 고유의 [ITypeLibResolver 인터페이스](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) 구현 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** TlbRef.h  
  
 **라이브러리:** TlbRef.lib  
  
 **.NET framework 버전:** 3.5, 3.0, 2.0  
  
## <a name="see-also"></a>참고자료

- [Tlbexp 도우미 함수](../../../../docs/framework/unmanaged-api/tlbexp/index.md)
- [LoadTypeLibEx 함수](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
