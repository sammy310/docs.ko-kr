---
title: ISymENCUnmanagedMethod::GetSourceExtentInDocument 메서드
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetSourceExtentInDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetSourceExtentInDocument
helpviewer_keywords:
- GetSourceExtentInDocument method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetSourceExtentInDocument method [.NET Framework debugging]
ms.assetid: 9c5566ab-4ec7-4b61-9753-839bb90ae78c
topic_type:
- apiref
ms.openlocfilehash: 2cd362279f5c5ff281b9674fe3d1e293ddbab5f1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707297"
---
# <a name="isymencunmanagedmethodgetsourceextentindocument-method"></a><span data-ttu-id="7d850-102">ISymENCUnmanagedMethod::GetSourceExtentInDocument 메서드</span><span class="sxs-lookup"><span data-stu-id="7d850-102">ISymENCUnmanagedMethod::GetSourceExtentInDocument Method</span></span>

<span data-ttu-id="7d850-103">특정 문서에서 메서드의 가장 작은 시작 줄과 가장 큰 끝 줄을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7d850-103">Gets the smallest start line and largest end line for the method in a specific document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d850-104">구문</span><span class="sxs-lookup"><span data-stu-id="7d850-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceExtentInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [out] ULONG32* pstartLine,  
    [out] ULONG32* pendLine);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d850-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7d850-105">Parameters</span></span>  

 `document`  
 <span data-ttu-id="7d850-106">진행 문서에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7d850-106">[in] A pointer to the document.</span></span>  
  
 `pstartLine`  
 <span data-ttu-id="7d850-107">제한이 시작 줄을 수신 하는에 대 한 포인터 `ULONG32` 입니다.</span><span class="sxs-lookup"><span data-stu-id="7d850-107">[out] A pointer to a `ULONG32` that receives the start line.</span></span>  
  
 `pendLine`  
 <span data-ttu-id="7d850-108">제한이 `ULONG32` 끝 줄을 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7d850-108">[out] A pointer to a `ULONG32` that receives the end line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7d850-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="7d850-109">Return Value</span></span>  

 <span data-ttu-id="7d850-110">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="7d850-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d850-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7d850-111">Requirements</span></span>  

 <span data-ttu-id="7d850-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="7d850-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d850-113">참조</span><span class="sxs-lookup"><span data-stu-id="7d850-113">See also</span></span>

- [<span data-ttu-id="7d850-114">ISymENCUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7d850-114">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)
