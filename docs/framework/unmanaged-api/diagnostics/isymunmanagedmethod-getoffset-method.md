---
title: ISymUnmanagedMethod::GetOffset 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetOffset
helpviewer_keywords:
- GetOffset method, ISymUnmanagedMethod interface [.NET Framework debugging]
- ISymUnmanagedMethod::GetOffset method [.NET Framework debugging]
ms.assetid: 8bf3cb62-89bf-4159-ad53-de606aba89e8
topic_type:
- apiref
ms.openlocfilehash: 14d4211b208482a399aa00430791b3efffda851e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699549"
---
# <a name="isymunmanagedmethodgetoffset-method"></a><span data-ttu-id="66fc5-102">ISymUnmanagedMethod::GetOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="66fc5-102">ISymUnmanagedMethod::GetOffset Method</span></span>

<span data-ttu-id="66fc5-103">문서 내의 지정 된 위치에 해당 하는이 메서드 내의 오프셋을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="66fc5-103">Returns the offset within this method that corresponds to a given position within a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66fc5-104">구문</span><span class="sxs-lookup"><span data-stu-id="66fc5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32                 line,  
    [in]  ULONG32                 column,  
    [out, retval] ULONG32*        pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66fc5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="66fc5-105">Parameters</span></span>  

 `document`  
 <span data-ttu-id="66fc5-106">진행 오프셋이 요청 된 문서에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="66fc5-106">[in] A pointer to the document for which the offset is requested.</span></span>  
  
 `line`  
 <span data-ttu-id="66fc5-107">진행 오프셋이 요청 된 문서 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="66fc5-107">[in] The document line for which the offset is requested.</span></span>  
  
 `column`  
 <span data-ttu-id="66fc5-108">진행 오프셋이 요청 된 문서 열입니다.</span><span class="sxs-lookup"><span data-stu-id="66fc5-108">[in] The document column for which the offset is requested.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="66fc5-109">제한이 오프셋을 수신 하는에 대 한 포인터 `ULONG32` 입니다.</span><span class="sxs-lookup"><span data-stu-id="66fc5-109">[out] A pointer to a `ULONG32` that receives the offsets.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="66fc5-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="66fc5-110">Return Value</span></span>  

 <span data-ttu-id="66fc5-111">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="66fc5-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66fc5-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="66fc5-112">Requirements</span></span>  

 <span data-ttu-id="66fc5-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="66fc5-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66fc5-114">참조</span><span class="sxs-lookup"><span data-stu-id="66fc5-114">See also</span></span>

- [<span data-ttu-id="66fc5-115">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="66fc5-115">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
