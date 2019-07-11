---
title: IMetaDataImport::ResolveTypeRef 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.ResolveTypeRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::ResolveTypeRef
helpviewer_keywords:
- ResolveTypeRef method [.NET Framework metadata]
- IMetaDataImport::ResolveTypeRef method [.NET Framework metadata]
ms.assetid: 556bccfb-61bc-4761-b1d5-de4b1c18a38f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cb8c232e63d1f3066737ff755d5911c185abe6fb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755375"
---
# <a name="imetadataimportresolvetyperef-method"></a>IMetaDataImport::ResolveTypeRef 메서드
확인을 <xref:System.Type> 지정한 TypeRef 토큰이 나타내는 참조 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ResolveTypeRef (  
   [in]  mdTypeRef       tr,  
   [in]  REFIID          riid,  
   [out] IUnknown        **ppIScope,  
   [out] mdTypeDef       *ptd  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `tr`  
 [in] 에 대 한 참조 된 형식 정보를 반환 하는 TypeRef 메타 데이터 토큰입니다.  
  
 `riid`  
 [in] 반환할 인터페이스의 IID `ppIScope`합니다. 일반적으로이 IID_IMetaDataImport 것입니다.  
  
 `ppIScope`  
 [out] 인터페이스 참조 형식이 정의 되어 있는 모듈 범위입니다.  
  
 `ptd`  
 [out] 참조 된 형식을 나타내는 TypeDef 토큰에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
  
> [!IMPORTANT]
>  여러 응용 프로그램 도메인이 로드 된 경우에이 메서드를 사용 하지 마십시오. 메서드는 응용 프로그램 도메인 경계를 고려 하지 않습니다. 여러 버전의 어셈블리가 로드 되 고 동일한 네임 스페이스를 사용 하 여 동일한 형식 포함을 하는 경우 메서드를 찾으면 첫 번째 유형은 모듈 범위를 반환 합니다.  
  
 `ResolveTypeRef` 메서드는 다른 모듈에서 형식 정의 검색 합니다. 형식 정의 있으면 `ResolveTypeRef` 인터페이스 형식에 대 한 TypeDef 토큰 뿐만 아니라 해당 모듈 범위를 반환 합니다.  
  
 형식 참조를 해결 해야 할 해결 범위가 AssemblyRef를 하는 경우는 `ResolveTypeRef` 메서드 중 하나를 호출 하 여 이미 열려 있는 메타 데이터 범위에만 일치 항목을 검색 합니다 [imetadatadispenser:: Openscope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)메서드 또는 [imetadatadispenser:: Openscopeonmemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) 메서드. 왜냐하면 `ResolveTypeRef` AssemblyRef 범위만 디스크 또는 전역 어셈블리 캐시에 어셈블리 저장 위치에서 확인할 수 없습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
