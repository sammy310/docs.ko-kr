---
title: IMetaDataTables 인터페이스
ms.date: 03/30/2017
api_name:
- IMetaDataTables
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables
helpviewer_keywords:
- IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 31272cce-506a-4f18-bcbf-01ee45e36356
topic_type:
- apiref
ms.openlocfilehash: 2105033e684ec172e24adfb14bcab7668b388af3
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501123"
---
# <a name="imetadatatables-interface"></a>IMetaDataTables 인터페이스
테이블에서 메타데이터 정보를 스토리지 및 검색하는 메서드를 제공합니다.  
  
## <a name="methods"></a>메서드  
  
|방법|설명|  
|------------|-----------------|  
|[GetBlob 메서드](imetadatatables-getblob-method.md)|지정 된 열 인덱스에 있는 BLOB (binary large object)에 대 한 포인터를 가져옵니다.|  
|[GetBlobHeapSize 메서드](imetadatatables-getblobheapsize-method.md)|BLOB 힙의 크기 (바이트)를 가져옵니다.|  
|[GetCodedTokenInfo 메서드](imetadatatables-getcodedtokeninfo-method.md)|지정 된 행 인덱스와 연결 된 토큰의 배열에 대 한 포인터를 가져옵니다.|  
|[GetColumn 메서드](imetadatatables-getcolumn-method.md)|지정 된 테이블 인덱스에 있는 테이블의 지정 된 열 인덱스에 있는 열에 포함 된 값에 대 한 포인터를 가져옵니다.|  
|[GetColumnInfo 메서드](imetadatatables-getcolumninfo-method.md)|지정 된 테이블의 지정 된 열에 대 한 데이터를 가져옵니다.|  
|[GetGuid 메서드](imetadatatables-getguid-method.md)|지정 된 인덱스의 행에서 GUID를 가져옵니다.|  
|[GetGuidHeapSize 메서드](imetadatatables-getguidheapsize-method.md)|GUID 힙의 크기 (바이트)를 가져옵니다.|  
|[GetNextBlob 메서드](imetadatatables-getnextblob-method.md)|테이블에서 다음 BLOB의 인덱스를 가져옵니다.|  
|[GetNextGuid 메서드](imetadatatables-getnextguid-method.md)|현재 테이블 열에서 다음 GUID 값의 인덱스를 가져옵니다.|  
|[GetNextString 메서드](imetadatatables-getnextstring-method.md)|현재 테이블 열에서 다음 문자열의 인덱스를 가져옵니다.|  
|[GetNextUserString 메서드](imetadatatables-getnextuserstring-method.md)|현재 테이블 열에 하드 코딩 된 다음 문자열이 포함 된 행의 인덱스를 가져옵니다.|  
|[GetNumTables 메서드](imetadatatables-getnumtables-method.md)|현재 인스턴스의 범위에 있는 테이블 수를 가져옵니다 `IMetaDataTables` .|  
|[GetRow 메서드](imetadatatables-getrow-method.md)|지정 된 테이블 인덱스에 있는 테이블의 지정 된 행 인덱스에 있는 행을 가져옵니다.|  
|[GetString 메서드](imetadatatables-getstring-method.md)|현재 참조 범위의 테이블 열에서 지정 된 인덱스에 있는 문자열을 가져옵니다.|  
|[GetStringHeapSize 메서드](imetadatatables-getstringheapsize-method.md)|문자열 힙의 크기 (바이트)를 가져옵니다.|  
|[GetTableIndex 메서드](imetadatatables-gettableindex-method.md)|지정 된 토큰이 참조 하는 테이블의 인덱스를 가져옵니다.|  
|[GetTableInfo 메서드](imetadatatables-gettableinfo-method.md)|지정 된 테이블 인덱스에 있는 테이블의 이름, 행 크기, 행 수, 열 수, 키 열 인덱스를 가져옵니다.|  
|[GetUserString 메서드](imetadatatables-getuserstring-method.md)|현재 범위에 있는 문자열 열의 지정 된 인덱스에서 하드 코드 된 문자열을 가져옵니다.|  
|[GetUserStringHeapSize 메서드](imetadatatables-getuserstringheapsize-method.md)|사용자 문자열 힙의 크기 (바이트)를 가져옵니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [메타데이터 인터페이스](metadata-interfaces.md)
- [IMetaDataTables2 인터페이스](imetadatatables2-interface.md)
