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
ms.openlocfilehash: d096101189d52401c407a4108c9c81e201d3f30d
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441944"
---
# <a name="isymencunmanagedmethodgetdocumentsformethodcount-method"></a><span data-ttu-id="6ff1e-102">ISymENCUnmanagedMethod::GetDocumentsForMethodCount 메서드</span><span class="sxs-lookup"><span data-stu-id="6ff1e-102">ISymENCUnmanagedMethod::GetDocumentsForMethodCount Method</span></span>
<span data-ttu-id="6ff1e-103">이 메서드에 줄이 있는 문서 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6ff1e-103">Gets the number of documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ff1e-104">구문</span><span class="sxs-lookup"><span data-stu-id="6ff1e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentsForMethodCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ff1e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6ff1e-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="6ff1e-106">제한이 `ULONG32`문서를 포함 하는 데 필요한 버퍼의 크기를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6ff1e-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6ff1e-107">Return Value</span><span class="sxs-lookup"><span data-stu-id="6ff1e-107">Return Value</span></span>  
 <span data-ttu-id="6ff1e-108">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="6ff1e-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ff1e-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6ff1e-109">Requirements</span></span>  
 <span data-ttu-id="6ff1e-110">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="6ff1e-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ff1e-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6ff1e-111">See also</span></span>

- [<span data-ttu-id="6ff1e-112">ISymENCUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6ff1e-112">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)
