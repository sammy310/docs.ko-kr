---
description: '자세히 알아보기: IMetaDataTables:: GetBlob 메서드'
title: IMetaDataTables::GetBlob 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetBlob
helpviewer_keywords:
- GetBlob method [.NET Framework metadata]
- IMetaDataTables::GetBlob method [.NET Framework metadata]
ms.assetid: 94667c1c-6d58-4aa7-b74e-530b11e2a276
topic_type:
- apiref
ms.openlocfilehash: 733f94c280283e00b644fe7811d450efbc7e1e7c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688392"
---
# <a name="imetadatatablesgetblob-method"></a>IMetaDataTables::GetBlob 메서드

지정 된 열 인덱스에 있는 BLOB (binary large object)에 대 한 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetBlob (  
    [in]  ULONG          ixBlob,  
    [out] ULONG          *pcbData,  
    [out] const void     **ppData  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `ixBlob`  
 진행 가져올 메모리 주소 `ppData` 입니다.  
  
 `pcbData`  
 제한이 의 크기 (바이트)에 대 한 포인터입니다 `ppData` .  
  
 `ppData`  
 제한이 검색 된 이진 데이터에 대 한 포인터에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataTables 인터페이스](imetadatatables-interface.md)
- [IMetaDataTables2 인터페이스](imetadatatables2-interface.md)
