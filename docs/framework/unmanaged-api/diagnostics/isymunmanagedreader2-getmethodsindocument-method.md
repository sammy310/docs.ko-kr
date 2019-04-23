---
title: ISymUnmanagedReader2::GetMethodsInDocument 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetMethodsInDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetMethodsInDocument
helpviewer_keywords:
- ISymUnmanagedReader2::GetMethodsInDocument method [.NET Framework debugging]
- GetMethodsInDocument method [.NET Framework debugging]
ms.assetid: c7ae84d6-81e8-4cb7-a1f9-d48b6cde5d79
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 28b240159c36b03b2c476f56f7e6ad7b33f20649
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59142351"
---
# <a name="isymunmanagedreader2getmethodsindocument-method"></a><span data-ttu-id="133e8-102">ISymUnmanagedReader2::GetMethodsInDocument 메서드</span><span class="sxs-lookup"><span data-stu-id="133e8-102">ISymUnmanagedReader2::GetMethodsInDocument Method</span></span>
<span data-ttu-id="133e8-103">제공 된 문서의 줄 정보가 있는 모든 메서드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="133e8-103">Gets every method that has line information in the provided document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="133e8-104">구문</span><span class="sxs-lookup"><span data-stu-id="133e8-104">Syntax</span></span>  
  
```  
HRESULT GetMethodsInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is(cMethod),  
        length_is(*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="133e8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="133e8-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="133e8-106">[in] 문서에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="133e8-106">[in] A pointer to the document.</span></span>  
  
 `cMethod`  
 <span data-ttu-id="133e8-107">[in] A `ULONG32` 의 크기를 나타내는 `pRetVal` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="133e8-107">[in] A `ULONG32` that indicates the size of the  `pRetVal` array.</span></span>  
  
 `pcMethod`  
 <span data-ttu-id="133e8-108">[out] 에 대 한 포인터를 `ULONG32` 메서드를 포함 하는 데 필요한 버퍼의 크기를 받는 합니다.</span><span class="sxs-lookup"><span data-stu-id="133e8-108">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the methods.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="133e8-109">[out] 메서드를 수신 하는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="133e8-109">[out] A pointer to the buffer that receives the methods.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="133e8-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="133e8-110">Return Value</span></span>  
 <span data-ttu-id="133e8-111">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="133e8-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="133e8-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="133e8-112">Requirements</span></span>  
 <span data-ttu-id="133e8-113">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="133e8-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="133e8-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="133e8-114">See also</span></span>

- [<span data-ttu-id="133e8-115">ISymUnmanagedReader2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="133e8-115">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
