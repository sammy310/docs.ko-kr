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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dd67d9faafedf4fb92c69618d4464ebb2ce47dcc
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72774253"
---
# <a name="imetadatatablesgetcolumninfo-method"></a>IMetaDataTables::GetColumnInfo 메서드
지정 된 테이블의 지정 된 열에 대 한 데이터를 가져옵니다.  
  
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
 진행 원하는 테이블의 인덱스입니다.  
  
 `ixCol`  
 진행 원하는 열의 인덱스입니다.  
  
 `poCol`  
 제한이 행에 있는 열의 오프셋에 대 한 포인터입니다.  
  
 `pcbCol`  
 제한이 열의 크기 (바이트)에 대 한 포인터입니다.  
  
 `pType`  
 제한이 열에 있는 값의 형식에 대 한 포인터입니다.  
  
 `ppName`  
 제한이 열 이름에 대 한 포인터에 대 한 포인터입니다.  
 
## <a name="remarks"></a>주의

반환 된 열 유형은 값 범위 내에 있습니다.

| pType                    | 설명   | 도우미 함수                   |
|--------------------------|---------------|-----------------------------------|
| `0`. `iRidMax`<br>(0, 63)   | 없앨           | **IsRidType**<br>**IsRidOrToken** |
| `iCodedToken`. `iCodedTokenMax`<br>(64.95) | 코딩 된 토큰 | **Iscoded Tokentype** <br>**IsRidOrToken** |
| `iSHORT` (96)            | Int16         | **IsFixedType**                   |
| `iUSHORT` (97)           | UInt16        | **IsFixedType**                   |
| `iLONG` (98)             | Int32         | **IsFixedType**                   |
| `iULONG` (99)            | UInt32        | **IsFixedType**                   |
| `iBYTE` (100)            | Byte          | **IsFixedType**                   |
| `iSTRING` (101)          | String        | **I박 Aptype**                    |
| `iGUID` (102)            | GUID          | **I박 Aptype**                    |
| `iBLOB` (103)            | Blob          | **I박 Aptype**                    |

*힙에* 저장 된 값 (즉, `IsHeapType == true`)은 다음을 사용 하 여 읽을 수 있습니다.

- `iSTRING`: **IMetadataTables. GetString**
- `iGUID`: **IMetadataTables**
- `iBLOB`: **IMetadataTables**

> [!IMPORTANT]
> 위의 표에 정의 된 상수를 사용 하려면 *cor* 헤더 파일에서 제공 `#define _DEFINE_META_DATA_META_CONSTANTS` 지시문을 포함 합니다.

## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [IMetaDataTables 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [IMetaDataTables2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
