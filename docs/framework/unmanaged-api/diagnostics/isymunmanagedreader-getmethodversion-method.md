---
description: '자세히 알아보기: ISymUnmanagedReader:: GetMethodVersion 메서드'
title: ISymUnmanagedReader::GetMethodVersion 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodVersion
helpviewer_keywords:
- GetMethodVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodVersion method [.NET Framework debugging]
ms.assetid: d6f9ac84-302a-4f5e-b990-e76f4269fceb
topic_type:
- apiref
ms.openlocfilehash: 027f65f858aab3e4ad0bc0bfbffd91f6118b80b2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764023"
---
# <a name="isymunmanagedreadergetmethodversion-method"></a>ISymUnmanagedReader::GetMethodVersion 메서드

메서드 버전을 가져옵니다. 메서드 버전은 1에서 시작 하 고 메서드를 다시 컴파일할 때마다 증가 합니다. 메서드를 변경 하지 않고도 다시 컴파일할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetMethodVersion (  
    [in]  ISymUnmanagedMethod* pMethod,  
    [out] int* version);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pMethod`  
 진행 버전을 가져올 메서드입니다.  
  
 `version`  
 제한이 메서드 버전을 받는 변수에 대 한 포인터입니다.  
  
## <a name="return-value"></a>Return Value  

 메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  

 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참고 항목

- [ISymUnmanagedReader 인터페이스](isymunmanagedreader-interface.md)
