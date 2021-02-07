---
description: '자세히 알아보기: ISymUnmanagedReader2:: GetMethodsInDocument 메서드'
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
ms.openlocfilehash: 1f75594a479edbf2e0160c9d3543384c0cbf68a0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763685"
---
# <a name="isymunmanagedreader2getmethodsindocument-method"></a><span data-ttu-id="2152c-103">ISymUnmanagedReader2::GetMethodsInDocument 메서드</span><span class="sxs-lookup"><span data-stu-id="2152c-103">ISymUnmanagedReader2::GetMethodsInDocument Method</span></span>

<span data-ttu-id="2152c-104">제공 된 문서에서 줄 정보를 포함 하는 모든 메서드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2152c-104">Gets every method that has line information in the provided document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2152c-105">구문</span><span class="sxs-lookup"><span data-stu-id="2152c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodsInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is(cMethod),  
        length_is(*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2152c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2152c-106">Parameters</span></span>  

 `document`  
 <span data-ttu-id="2152c-107">진행 문서에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2152c-107">[in] A pointer to the document.</span></span>  
  
 `cMethod`  
 <span data-ttu-id="2152c-108">진행 `ULONG32` 배열의 크기를 나타내는입니다  `pRetVal` .</span><span class="sxs-lookup"><span data-stu-id="2152c-108">[in] A `ULONG32` that indicates the size of the  `pRetVal` array.</span></span>  
  
 `pcMethod`  
 <span data-ttu-id="2152c-109">제한이 `ULONG32` 메서드를 포함 하는 데 필요한 버퍼의 크기를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2152c-109">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the methods.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="2152c-110">제한이 메서드를 받는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2152c-110">[out] A pointer to the buffer that receives the methods.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2152c-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="2152c-111">Return Value</span></span>  

 <span data-ttu-id="2152c-112">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="2152c-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2152c-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2152c-113">Requirements</span></span>  

 <span data-ttu-id="2152c-114">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="2152c-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2152c-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2152c-115">See also</span></span>

- [<span data-ttu-id="2152c-116">ISymUnmanagedReader2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2152c-116">ISymUnmanagedReader2 Interface</span></span>](isymunmanagedreader2-interface.md)
