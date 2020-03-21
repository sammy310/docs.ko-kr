---
title: IMetaDataTables::GetColumn 메서드
ms.date: 02/25/2019
api_name:
- IMetaDataTables.GetColumn
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetColumn
helpviewer_keywords:
- IMetaDataTables::GetColumn method [.NET Framework metadata]
- GetColumn method [.NET Framework metadata]
ms.assetid: 1032055b-cabb-45c5-a50e-7e853201b175
topic_type:
- apiref
ms.openlocfilehash: f43d4d1547cbe92f325950e1697dada83b42c4f3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177136"
---
# <a name="imetadatatablesgetcolumn-method"></a>IMetaDataTables::GetColumn 메서드
지정된 열의 셀에 포함된 값에 대한 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetColumn (
    [in]  ULONG   ixTbl,  
    [in]  ULONG   ixCol,  
    [in]  ULONG   rid,  
    [out] ULONG   *pVal  
);  
```  
  
## <a name="parameters"></a>매개 변수

 `ixTbl`  
 【인】 테이블의 인덱스입니다.  
  
 `ixCol`  
 【인】 테이블의 열 인덱스입니다.  
  
 `rid`  
 【인】 테이블의 행 인덱스입니다.  
  
 `pVal`  
 【아웃】 셀의 값에 대한 포인터입니다.  

## <a name="remarks"></a>설명

통해 `pVal` 반환되는 값의 해석은 열의 형식에 따라 다릅니다. 열 유형은 [IMetaDataTables.GetColumnInfo](imetadatatables-getcolumninfo-method.md)를 호출하여 결정할 수 있습니다.

- **GetColumn** 메서드는 **자동으로 코드 제거** 또는 **CodedToken** 형식의 열을 `mdToken` 전체 32비트 값으로 변환합니다.
- 또한 8비트 또는 16비트 값을 전체 32비트 값으로 자동으로 변환합니다.
- *힙* 유형 열의 경우 반환된 *pVal은* 해당 힙에 인덱스가 됩니다.

| 열 유형              | pVal 포함 | 주석                          |
|--------------------------|---------------|-----------------------------------|
| `0`..`iRidMax`<br>(0..63)  | mdToken     | *pVal에는* 전체 토큰이 포함됩니다. 이 함수는 Rid를 전체 토큰으로 자동으로 변환합니다. |
| `iCodedToken`..`iCodedTokenMax`<br>(64..95) | mdToken | 반환 *시, pVal* 전체 토큰을 포함 합니다. 이 함수는 CodedToken을 전체 토큰으로 자동으로 압축 해제합니다. |
| `iSHORT`(96)            | Int16         | 자동으로 32비트로 확장된 기호입니다.  |
| `iUSHORT`(97)           | UInt16        | 자동으로 32비트로 확장된 기호입니다.  |
| `iLONG`(98)             | Int32         |                                        |
| `iULONG`(99)            | UInt32        |                                        |
| `iBYTE`(100)            | Byte          | 자동으로 32비트로 확장된 기호입니다.  |
| `iSTRING`(101)          | 문자열 힙 인덱스 | *pVal은* 문자열 힙에 대한 인덱스입니다. [IMetadataTables::GetString을](imetadatatables-getstring-method.md) 사용하여 실제 열 문자열 값을 가져옵니다. |
| `iGUID`(102)            | Guid 힙 인덱스 | *pVal은* Guid 힙에 대한 인덱스입니다. [I메타데이터 테이블 사용::GetGuid를](imetadatatables-getguid-method.md) 사용하여 실제 열 Guid 값을 가져옵니다. |
| `iBLOB`(103)            | Blob 힙 인덱스 | *pVal은* Blob 힙에 대한 인덱스입니다. [I메타데이터 테이블 사용::GetBlob에서](imetadatatables-getblob-method.md) 실제 열 Blob 값을 가져옵니다. |
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 사용  
  
 **.NET 프레임워크 버전**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataTables 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [IMetaDataTables2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
