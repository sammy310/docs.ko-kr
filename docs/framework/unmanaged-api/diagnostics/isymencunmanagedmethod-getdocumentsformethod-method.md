---
description: '자세히 알아보기: ISymENCUnmanagedMethod:: GetDocumentsForMethod 메서드'
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
ms.openlocfilehash: 01c7280abe437266618d96c6e195e61a4f830131
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721543"
---
# <a name="isymencunmanagedmethodgetdocumentsformethod-method"></a><span data-ttu-id="b862e-103">ISymENCUnmanagedMethod::GetDocumentsForMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="b862e-103">ISymENCUnmanagedMethod::GetDocumentsForMethod Method</span></span>

<span data-ttu-id="b862e-104">이 메서드에 줄이 있는 문서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b862e-104">Gets the documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b862e-105">구문</span><span class="sxs-lookup"><span data-stu-id="b862e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentsForMethod(  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,
    [in, size_is(cDocs)] ISymUnmanagedDocument* documents[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b862e-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b862e-106">Parameters</span></span>  

 `cDocs`  
 <span data-ttu-id="b862e-107">진행 가 가리키는 버퍼의 길이입니다 `pcDocs` .</span><span class="sxs-lookup"><span data-stu-id="b862e-107">[in] The length of the buffer pointed to by `pcDocs`.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="b862e-108">제한이 `ULONG32` 문서를 포함 하는 데 필요한 버퍼의 크기 (문자 수)를 받는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b862e-108">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the documents.</span></span>  
  
 `documents`  
 <span data-ttu-id="b862e-109">진행 문서를 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="b862e-109">[in] The buffer that contains the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b862e-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="b862e-110">Return Value</span></span>  

 <span data-ttu-id="b862e-111">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="b862e-111">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b862e-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b862e-112">Requirements</span></span>  

 <span data-ttu-id="b862e-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="b862e-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b862e-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b862e-114">See also</span></span>

- [<span data-ttu-id="b862e-115">ISymENCUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b862e-115">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)
