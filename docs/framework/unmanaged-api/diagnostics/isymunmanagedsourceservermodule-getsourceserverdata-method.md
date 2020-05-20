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
ms.openlocfilehash: 9a3a6c07a9cace0ac9834cdb05925a301285204c
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615321"
---
# <a name="isymunmanagedsourceservermodulegetsourceserverdata-method"></a>ISymUnmanagedSourceServerModule::GetSourceServerData 메서드
모듈에 대 한 원본 서버 데이터를 반환 합니다. 호출자는를 사용 하 여 리소스를 해제 해야 합니다 `CoTaskMemFree` .  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetSourceServerData(  
    [out] ULONG* pDataByteCount,
    [out, size_is (, *pDataByteCount)] BYTE** ppData);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pDataByteCount`  
 제한이 `ULONG32`원본 서버 데이터의 크기 (바이트)를 수신 하는에 대 한 포인터입니다.  
  
 `ppData`  
 제한이 반환 된 값에 대 한 포인터 `pDataByteCount` 입니다.  
  
## <a name="return-value"></a>Return Value  
 메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참고 항목

- [ISymUnmanagedSourceServerModule 인터페이스](isymunmanagedsourceservermodule-interface.md)
