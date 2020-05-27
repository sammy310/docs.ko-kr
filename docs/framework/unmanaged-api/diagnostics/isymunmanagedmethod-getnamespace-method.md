---
title: ISymUnmanagedMethod::GetNamespace 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetNamespace
helpviewer_keywords:
- ISymUnmanagedMethod::GetNamespace method [.NET Framework debugging]
- GetNamespace method [.NET Framework debugging]
ms.assetid: 7fbbac42-b966-406d-9ae9-67bf3aea74ce
topic_type:
- apiref
ms.openlocfilehash: cda30f3c73bf75c37ff79fc415e02382b053807e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614489"
---
# <a name="isymunmanagedmethodgetnamespace-method"></a><span data-ttu-id="49127-102">ISymUnmanagedMethod::GetNamespace 메서드</span><span class="sxs-lookup"><span data-stu-id="49127-102">ISymUnmanagedMethod::GetNamespace Method</span></span>
<span data-ttu-id="49127-103">이 메서드가 정의 된 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="49127-103">Gets the namespace within which this method is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49127-104">구문</span><span class="sxs-lookup"><span data-stu-id="49127-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespace(  
   [out] ISymUnmanagedNamespace  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49127-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="49127-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="49127-106">제한이 반환 된 [ISymUnmanagedNamespace](isymunmanagednamespace-interface.md) interface로 설정 된 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="49127-106">[out] A pointer that is set to the returned [ISymUnmanagedNamespace](isymunmanagednamespace-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="49127-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="49127-107">Return Value</span></span>  
 <span data-ttu-id="49127-108">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="49127-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49127-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="49127-109">Requirements</span></span>  
 <span data-ttu-id="49127-110">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="49127-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49127-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="49127-111">See also</span></span>

- [<span data-ttu-id="49127-112">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="49127-112">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
