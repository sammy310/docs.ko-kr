---
title: IMetaDataTables::GetRow 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetRow
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetRow
helpviewer_keywords:
- IMetaDataTables::GetRow method [.NET Framework metadata]
- GetRow method [.NET Framework metadata]
ms.assetid: a7408d51-0bce-45a2-b58f-da4660bbc039
topic_type:
- apiref
ms.openlocfilehash: 71f6c496816fec1a7537f5ccdfdc1b47d17da871
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177110"
---
# <a name="imetadatatablesgetrow-method"></a>IMetaDataTables::GetRow 메서드
지정된 테이블 인덱스의 테이블에서 지정된 행 인덱스에서 행을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetRow (
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `ixTbl`  
 【인】 행을 검색할 테이블의 인덱스입니다.  
  
 `rid`  
 【인】 얻을 행의 인덱스입니다.  
  
 `ppRow`  
 【아웃】 행에 대한 포인터에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  

  일관된 결과를 반환하지 않으므로 이 메서드를 사용하지 않는 것이 좋습니다. GUID 테이블에 대한 자세한 내용은 CLI(공통 언어 인프라) 설명서, 특히 "파티션 II: 메타데이터 정의 및 의미 체계"를 참조하십시오. 이 설명서는 온라인으로 사용할 수 있습니다. [ECMA C# 및 공통 언어 인프라 표준](../../../standard/components.md#applicable-standards) 및 표준 [ECMA-335 - 공통 언어 인프라(CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm)참조.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 사용  
  
 **.NET 프레임워크 버전**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataTables 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [IMetaDataTables2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
