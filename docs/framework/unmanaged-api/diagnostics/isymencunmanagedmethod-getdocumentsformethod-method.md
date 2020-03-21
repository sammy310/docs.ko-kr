---
title: ISymENCUnmanagedMethod::GetDocumentsForMethod 메서드
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetDocumentsForMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetDocumentsForMethod
helpviewer_keywords:
- GetDocumentsForMethod method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetDocumentsForMethod method [.NET Framework debugging]
ms.assetid: bd6ccde5-d578-48d8-abed-b474fbd48d13
topic_type:
- apiref
ms.openlocfilehash: 97f0d81c389ffd0bd8a69df2ca39322d726f98bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176632"
---
# <a name="isymencunmanagedmethodgetdocumentsformethod-method"></a><span data-ttu-id="b35be-102">ISymENCUnmanagedMethod::GetDocumentsForMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="b35be-102">ISymENCUnmanagedMethod::GetDocumentsForMethod Method</span></span>
<span data-ttu-id="b35be-103">이 메서드에 줄이 있는 문서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b35be-103">Gets the documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b35be-104">구문</span><span class="sxs-lookup"><span data-stu-id="b35be-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentsForMethod(  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,
    [in, size_is(cDocs)] ISymUnmanagedDocument* documents[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b35be-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b35be-105">Parameters</span></span>  
 `cDocs`  
 <span data-ttu-id="b35be-106">【인】 을 가리키는 버퍼의 `pcDocs`길이입니다.</span><span class="sxs-lookup"><span data-stu-id="b35be-106">[in] The length of the buffer pointed to by `pcDocs`.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="b35be-107">【아웃】 문서를 포함하는 `ULONG32` 데 필요한 버퍼의 크기(문자)를 받는 a에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b35be-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the documents.</span></span>  
  
 `documents`  
 <span data-ttu-id="b35be-108">【인】 문서를 포함하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="b35be-108">[in] The buffer that contains the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b35be-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="b35be-109">Return Value</span></span>  
 <span data-ttu-id="b35be-110">메서드가 성공하면 S_OK. 그렇지 않으면 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="b35be-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b35be-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b35be-111">Requirements</span></span>  
 <span data-ttu-id="b35be-112">**헤더:** 코르심.idl, 코르심.h</span><span class="sxs-lookup"><span data-stu-id="b35be-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b35be-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b35be-113">See also</span></span>

- [<span data-ttu-id="b35be-114">ISymENCUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b35be-114">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
