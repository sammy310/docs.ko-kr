---
title: IMetaDataTables::GetColumnInfo 메서드
ms.date: 10/10/2019
api_name:
- IMetaDataTables.GetColumnInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetColumnInfo
helpviewer_keywords:
- IMetaDataTables::GetColumnInfo method [.NET Framework metadata]
- GetColumnInfo method [.NET Framework metadata]
ms.assetid: 68c160ea-ae7d-4750-985d-a038b2c8e7d9
topic_type:
- apiref
ms.openlocfilehash: cc8aac32149fed952737d928e16a8f6efc448c79
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177130"
---
# <a name="imetadatatablesgetcolumninfo-method"></a>IMetaDataTables::GetColumnInfo 메서드
지정된 테이블에서 지정된 열에 대한 데이터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetColumnInfo (
    [in]  ULONG        ixTbl,  
    [in]  ULONG        ixCol,  
    [out] ULONG        *poCol,  
    [out] ULONG        *pcbCol,  
    [out] ULONG        *pType,  
    [out] const char   **ppName  
);  
```  
  
## <a name="parameters"></a>매개 변수
=======

 `ixTbl`  
 【인】 원하는 테이블의 인덱스입니다.  
  
 `ixCol`  
 【인】 원하는 열의 인덱스입니다.  
  
 `poCol`  
 【아웃】 행의 열 오프셋에 대한 포인터입니다.  
  
 `pcbCol`  
 【아웃】 열의 크기에 대한 포인터(바이트)입니다.  
  
 `pType`  
 【아웃】 열의 값 유형에 대한 포인터입니다.  
  
 `ppName`  
 【아웃】 열 이름에 대한 포인터에 대한 포인터입니다.  

## <a name="remarks"></a>설명

반환된 열 유형은 값 범위 내에 있습니다.

| p유형                    | Description   | 도우미 기능                   |
|--------------------------|---------------|-----------------------------------|
| `0`..`iRidMax`<br>(0..63)   | 제거           | **이스리드 타입**<br>**이리도르 토큰** |
| `iCodedToken`..`iCodedTokenMax`<br>(64..95) | 코딩된 토큰 | **IsCoded토큰 타입** <br>**이리도르 토큰** |
| `iSHORT`(96)            | Int16         | **IsfixedType**                   |
| `iUSHORT`(97)           | UInt16        | **IsfixedType**                   |
| `iLONG`(98)             | Int32         | **IsfixedType**                   |
| `iULONG`(99)            | UInt32        | **IsfixedType**                   |
| `iBYTE`(100)            | Byte          | **IsfixedType**                   |
| `iSTRING`(101)          | String        | **이시압 타입**                    |
| `iGUID`(102)            | Guid          | **이시압 타입**                    |
| `iBLOB`(103)            | Blob          | **이시압 타입**                    |

*힙에* 저장된 값(즉,)을 `IsHeapType == true`사용하여 읽을 수 있습니다.

- `iSTRING`: **I메타데이터 테이블.겟스트링**
- `iGUID`: **I메타데이터 테이블.겟가드**
- `iBLOB`: **I메타데이터 테이블.겟블블**

> [!IMPORTANT]
> 위의 표에 정의된 상수를 사용하려면 `#define _DEFINE_META_DATA_META_CONSTANTS` *cor.h* 헤더 파일에서 제공하는 지시문을 포함하십시오.

## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataTables 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [IMetaDataTables2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
