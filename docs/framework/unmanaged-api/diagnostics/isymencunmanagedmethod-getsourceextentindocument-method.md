---
description: '자세히 알아보기: ISymENCUnmanagedMethod:: GetSourceExtentInDocument 메서드'
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
ms.openlocfilehash: 6fa9edb524a59b4420ebc737eb8d34eaf0c5c873
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737885"
---
# <a name="isymencunmanagedmethodgetsourceextentindocument-method"></a><span data-ttu-id="6a796-103">ISymENCUnmanagedMethod::GetSourceExtentInDocument 메서드</span><span class="sxs-lookup"><span data-stu-id="6a796-103">ISymENCUnmanagedMethod::GetSourceExtentInDocument Method</span></span>

<span data-ttu-id="6a796-104">특정 문서에서 메서드의 가장 작은 시작 줄과 가장 큰 끝 줄을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6a796-104">Gets the smallest start line and largest end line for the method in a specific document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a796-105">구문</span><span class="sxs-lookup"><span data-stu-id="6a796-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceExtentInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [out] ULONG32* pstartLine,  
    [out] ULONG32* pendLine);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a796-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6a796-106">Parameters</span></span>  

 `document`  
 <span data-ttu-id="6a796-107">진행 문서에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6a796-107">[in] A pointer to the document.</span></span>  
  
 `pstartLine`  
 <span data-ttu-id="6a796-108">제한이 시작 줄을 수신 하는에 대 한 포인터 `ULONG32` 입니다.</span><span class="sxs-lookup"><span data-stu-id="6a796-108">[out] A pointer to a `ULONG32` that receives the start line.</span></span>  
  
 `pendLine`  
 <span data-ttu-id="6a796-109">제한이 `ULONG32` 끝 줄을 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6a796-109">[out] A pointer to a `ULONG32` that receives the end line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6a796-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="6a796-110">Return Value</span></span>  

 <span data-ttu-id="6a796-111">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="6a796-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a796-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6a796-112">Requirements</span></span>  

 <span data-ttu-id="6a796-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="6a796-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a796-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6a796-114">See also</span></span>

- [<span data-ttu-id="6a796-115">ISymENCUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6a796-115">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)
