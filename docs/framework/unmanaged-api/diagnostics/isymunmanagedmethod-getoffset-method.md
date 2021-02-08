---
description: '자세히 알아보기: ISymUnmanagedMethod:: GetOffset 메서드'
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
ms.openlocfilehash: 3bc7154a47a38fd2cbadc62921f6e57f7901087e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790128"
---
# <a name="isymunmanagedmethodgetoffset-method"></a><span data-ttu-id="9cb9c-103">ISymUnmanagedMethod::GetOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="9cb9c-103">ISymUnmanagedMethod::GetOffset Method</span></span>

<span data-ttu-id="9cb9c-104">문서 내의 지정 된 위치에 해당 하는이 메서드 내의 오프셋을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cb9c-104">Returns the offset within this method that corresponds to a given position within a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cb9c-105">구문</span><span class="sxs-lookup"><span data-stu-id="9cb9c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32                 line,  
    [in]  ULONG32                 column,  
    [out, retval] ULONG32*        pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9cb9c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9cb9c-106">Parameters</span></span>  

 `document`  
 <span data-ttu-id="9cb9c-107">진행 오프셋이 요청 된 문서에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9cb9c-107">[in] A pointer to the document for which the offset is requested.</span></span>  
  
 `line`  
 <span data-ttu-id="9cb9c-108">진행 오프셋이 요청 된 문서 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="9cb9c-108">[in] The document line for which the offset is requested.</span></span>  
  
 `column`  
 <span data-ttu-id="9cb9c-109">진행 오프셋이 요청 된 문서 열입니다.</span><span class="sxs-lookup"><span data-stu-id="9cb9c-109">[in] The document column for which the offset is requested.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="9cb9c-110">제한이 오프셋을 수신 하는에 대 한 포인터 `ULONG32` 입니다.</span><span class="sxs-lookup"><span data-stu-id="9cb9c-110">[out] A pointer to a `ULONG32` that receives the offsets.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9cb9c-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="9cb9c-111">Return Value</span></span>  

 <span data-ttu-id="9cb9c-112">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="9cb9c-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cb9c-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9cb9c-113">Requirements</span></span>  

 <span data-ttu-id="9cb9c-114">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="9cb9c-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cb9c-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9cb9c-115">See also</span></span>

- [<span data-ttu-id="9cb9c-116">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9cb9c-116">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
