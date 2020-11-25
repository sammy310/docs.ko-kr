---
title: IMetaDataTables2::GetMetaDataStreamInfo 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables2.GetMetaDataStreamInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables2::GetMetaDataStreamInfo
helpviewer_keywords:
- GetMetaDataStreamInfo method [.NET Framework metadata]
- IMetaDataTables2::GetMetaDataStreamInfo method [.NET Framework metadata]
ms.assetid: 8b280627-cc74-4789-95da-1fefc966de05
topic_type:
- apiref
ms.openlocfilehash: 21fc79f62dba4b16a7a067dff8fb9dcc795c9d35
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708727"
---
# <a name="imetadatatables2getmetadatastreaminfo-method"></a>IMetaDataTables2::GetMetaDataStreamInfo 메서드

지정 된 인덱스에 있는 메타 데이터 스트림의 이름, 크기 및 내용을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetMetaDataStreamInfo (  
   [in]  ULONG        ix,  
   [out] const char   **ppchName,  
   [out] const void   **ppv,  
   [out] ULONG        *pcb  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `ix`  
 진행 요청 된 메타 데이터 스트림의 인덱스입니다.  
  
 `ppchName`  
 제한이 스트림 이름에 대 한 포인터입니다.  
  
 `ppv`  
 제한이 메타 데이터 스트림에 대 한 포인터입니다.  
  
 `pcb`  
 제한이 의 크기 (바이트)입니다 `ppv` .  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [IMetaDataTables2 인터페이스](imetadatatables2-interface.md)
- [IMetaDataTables 인터페이스](imetadatatables-interface.md)
