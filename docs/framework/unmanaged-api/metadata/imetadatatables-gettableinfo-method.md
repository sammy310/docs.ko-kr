---
description: '자세히 알아보기: IMetaDataTables:: GetTableInfo 메서드'
title: IMetaDataTables::GetTableInfo 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetTableInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetTableInfo
helpviewer_keywords:
- IMetaDataTables::GetTableInfo method [.NET Framework metadata]
- GetTableInfo method [.NET Framework metadata]
ms.assetid: 50cbe557-2322-41aa-8e0d-f967602eaa0f
topic_type:
- apiref
ms.openlocfilehash: 3929f91c15b5c1fc22ac3ad4b17cbaa38a08533a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99687651"
---
# <a name="imetadatatablesgettableinfo-method"></a>IMetaDataTables::GetTableInfo 메서드

지정 된 테이블의 이름, 행 크기, 행 수, 열 수, 키 열 인덱스를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetTableInfo (  
    [in]  ULONG       ixTbl,  
    [out] ULONG       *pcbRow,  
    [out] ULONG       *pcRows,  
    [out] ULONG       *pcCols,  
    [out] ULONG       *piKey,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `ixTbl`  
 진행 반환할 속성을 가진 테이블의 식별자입니다.  
  
 `pcbRow`  
 제한이 테이블 행의 크기 (바이트)에 대 한 포인터입니다.  
  
 `pcRows`  
 제한이 테이블의 행 수에 대 한 포인터입니다.  
  
 `pcCols`  
 제한이 테이블의 열 수에 대 한 포인터입니다.  
  
 `piKey`  
 제한이 키 열의 인덱스에 대 한 포인터 이거나, 테이블에 키 열이 없으면-1입니다.  
  
 `ppName`  
 제한이 테이블 이름에 대 한 포인터에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataTables 인터페이스](imetadatatables-interface.md)
- [IMetaDataTables2 인터페이스](imetadatatables2-interface.md)
