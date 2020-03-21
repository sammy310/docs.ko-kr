---
title: StrongNameFreeBuffer 함수
ms.date: 03/30/2017
api_name:
- StrongNameFreeBuffer
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameFreeBuffer
helpviewer_keywords:
- StrongNameFreeBuffer function [.NET Framework strong naming]
ms.assetid: eda21ecf-4734-4f92-aaba-9f34884385db
topic_type:
- apiref
ms.openlocfilehash: 50e3cc6e677de45be9256a2a818ebd6ed7d8b843
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176918"
---
# <a name="strongnamefreebuffer-function"></a>StrongNameFreeBuffer 함수
[StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md) 또는 [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md)과 같은 강력한 이름 함수에 대한 이전 호출로 할당된 메모리를 해제합니다.  
  
 이 함수는 더 이상 사용되지 않습니다. 대신 [ICLRStrongName::StrongNameFreeBuffer](../hosting/iclrstrongname-strongnamefreebuffer-method.md) 메서드를 사용합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
VOID StrongNameFreeBuffer (
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pbMemory`  
 【인】 해제할 메모리에 대한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 스트롱네임  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [StrongNameFreeBuffer 메서드](../hosting/iclrstrongname-strongnamefreebuffer-method.md)
- [ICLRStrongName 인터페이스](../hosting/iclrstrongname-interface.md)
