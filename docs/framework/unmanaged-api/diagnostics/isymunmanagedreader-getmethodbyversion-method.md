---
title: ISymUnmanagedReader::GetMethodByVersion 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodByVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodByVersion
helpviewer_keywords:
- ISymUnmanagedReader::GetMethodByVersion method [.NET Framework debugging]
- GetMethodByVersion method [.NET Framework debugging]
ms.assetid: 6ddb0631-4569-41b3-93e4-50fdfaa486dc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d4bc763d908156f3bbf8998c13073820686903f6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986377"
---
# <a name="isymunmanagedreadergetmethodbyversion-method"></a>ISymUnmanagedReader::GetMethodByVersion 메서드
지정 된 메서드 토큰 및 편집 복사 버전 번호를 기호 판독기 메서드를 가져옵니다. 버전 번호는 1부터 시작 하 고 메서드를 편집 하 고 복사 작업의 결과로 변경 될 때마다 증가 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetMethodByVersion (  
    [in]  mdMethodDef  token,  
    [in]  int  version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a>매개 변수  
 `token`  
 [in] 메서드 토큰입니다.  
  
 `version`  
 [in] 메서드 버전입니다.  
  
 `pRetVal`  
 [out] 반환 되는 인터페이스 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고자료

- [ISymUnmanagedReader 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
