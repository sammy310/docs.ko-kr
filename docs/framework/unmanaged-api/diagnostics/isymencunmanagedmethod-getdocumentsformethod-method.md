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
ms.openlocfilehash: 49023424c21fced1c49b16ecdbea93c654b5e883
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448388"
---
# <a name="isymencunmanagedmethodgetdocumentsformethod-method"></a><span data-ttu-id="95e03-102">ISymENCUnmanagedMethod::GetDocumentsForMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="95e03-102">ISymENCUnmanagedMethod::GetDocumentsForMethod Method</span></span>
<span data-ttu-id="95e03-103">이 메서드에 줄이 있는 문서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="95e03-103">Gets the documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95e03-104">구문</span><span class="sxs-lookup"><span data-stu-id="95e03-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentsForMethod(  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,   
    [in, size_is(cDocs)] ISymUnmanagedDocument* documents[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95e03-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="95e03-105">Parameters</span></span>  
 `cDocs`  
 <span data-ttu-id="95e03-106">진행 `pcDocs`가 가리키는 버퍼의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="95e03-106">[in] The length of the buffer pointed to by `pcDocs`.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="95e03-107">제한이 문서를 포함 하는 데 필요한 버퍼의 크기 (문자 수)를 수신 하는 `ULONG32`에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="95e03-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the documents.</span></span>  
  
 `documents`  
 <span data-ttu-id="95e03-108">진행 문서를 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="95e03-108">[in] The buffer that contains the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="95e03-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="95e03-109">Return Value</span></span>  
 <span data-ttu-id="95e03-110">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="95e03-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95e03-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="95e03-111">Requirements</span></span>  
 <span data-ttu-id="95e03-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="95e03-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95e03-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="95e03-113">See also</span></span>

- [<span data-ttu-id="95e03-114">ISymENCUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="95e03-114">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
