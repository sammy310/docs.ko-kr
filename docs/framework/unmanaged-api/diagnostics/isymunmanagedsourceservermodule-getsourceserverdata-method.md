---
title: ISymUnmanagedSourceServerModule::GetSourceServerData 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSourceServerModule.GetSourceServerData
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSourceServerModule::GetSourceServerData
helpviewer_keywords:
- ISymUnmanagedSourceServerModule::GetSourceServerData method [.NET Framework debugging]
- GetSourceServerData method [.NET Framework debugging]
ms.assetid: 20bdf8ff-2d15-4c64-8950-6888f642d6c0
topic_type:
- apiref
ms.openlocfilehash: 6904271ed90cf733b9221178927bc680d76b58a6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176580"
---
# <a name="isymunmanagedsourceservermodulegetsourceserverdata-method"></a>ISymUnmanagedSourceServerModule::GetSourceServerData 메서드
모듈의 원본 서버 데이터를 반환합니다. 호출자는 을 사용하여 `CoTaskMemFree`리소스를 해제해야 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetSourceServerData(  
    [out] ULONG* pDataByteCount,
    [out, size_is (, *pDataByteCount)] BYTE** ppData);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pDataByteCount`  
 【아웃】 원본 서버 `ULONG32` 데이터의 크기(바이트)를 받는 에 대한 포인터입니다.  
  
 `ppData`  
 【아웃】 반환된 `pDataByteCount` 값에 대한 포인터입니다.  
  
## <a name="return-value"></a>Return Value  
 메서드가 성공하면 S_OK. 그렇지 않으면 E_FAIL 또는 다른 오류 코드가 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** 코르심.idl, 코르심.h  
  
## <a name="see-also"></a>참고 항목

- [ISymUnmanagedSourceServerModule 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)
