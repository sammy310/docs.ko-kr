---
title: ISymENCUnmanagedMethod::GetDocumentsForMethodCount 메서드
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetDocumentsForMethodCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetDocumentsForMethodCount
helpviewer_keywords:
- GetDocumentsForMethodCount method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetDocumentsForMethodCount method [.NET Framework debugging]
ms.assetid: cc1a823a-3ff3-4a33-b641-96edc93d2b17
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bf8cca7751dd9705fd3c4371e36e836ca19be5c9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736216"
---
# <a name="isymencunmanagedmethodgetdocumentsformethodcount-method"></a><span data-ttu-id="ba3a6-102">ISymENCUnmanagedMethod::GetDocumentsForMethodCount 메서드</span><span class="sxs-lookup"><span data-stu-id="ba3a6-102">ISymENCUnmanagedMethod::GetDocumentsForMethodCount Method</span></span>
<span data-ttu-id="ba3a6-103">줄에는이 메서드는 문서 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ba3a6-103">Gets the number of documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba3a6-104">구문</span><span class="sxs-lookup"><span data-stu-id="ba3a6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentsForMethodCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba3a6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ba3a6-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="ba3a6-106">[out] 에 대 한 포인터를 `ULONG32` 문서를 포함 하는 데 필요한 버퍼의 크기를 받는 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba3a6-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ba3a6-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="ba3a6-107">Return Value</span></span>  
 <span data-ttu-id="ba3a6-108">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="ba3a6-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba3a6-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ba3a6-109">Requirements</span></span>  
 <span data-ttu-id="ba3a6-110">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ba3a6-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba3a6-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="ba3a6-111">See also</span></span>

- [<span data-ttu-id="ba3a6-112">ISymENCUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ba3a6-112">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
