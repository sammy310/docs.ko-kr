---
description: '자세히 알아보기: ISymUnmanagedDocument:: FindClosestLine 메서드'
title: ISymUnmanagedDocument::FindClosestLine 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.FindClosestLine
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::FindClosestLine
helpviewer_keywords:
- FindClosestLine method [.NET Framework debugging]
- ISymUnmanagedDocument::FindClosestLine method [.NET Framework debugging]
ms.assetid: 628f2a04-e529-407d-841e-3b3da219a9cb
topic_type:
- apiref
ms.openlocfilehash: 0409a5cc29bf148a49a5267d34662f763fc302d9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737833"
---
# <a name="isymunmanageddocumentfindclosestline-method"></a><span data-ttu-id="5ecf7-103">ISymUnmanagedDocument::FindClosestLine 메서드</span><span class="sxs-lookup"><span data-stu-id="5ecf7-103">ISymUnmanagedDocument::FindClosestLine Method</span></span>

<span data-ttu-id="5ecf7-104">이 문서에서 시퀀스 위치가 될 수도 있고 그렇지 않을 수도 있는 줄을 지정 하 여 시퀀스 위치인 가장 가까운 줄을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ecf7-104">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ecf7-105">구문</span><span class="sxs-lookup"><span data-stu-id="5ecf7-105">Syntax</span></span>  
  
```cpp  
HRESULT FindClosestLine(  
    [in]  ULONG32  line,  
    [out, retval] ULONG32*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ecf7-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5ecf7-106">Parameters</span></span>  

 `line`  
 <span data-ttu-id="5ecf7-107">진행 이 문서의 한 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="5ecf7-107">[in] A line in this document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="5ecf7-108">제한이 줄을 받는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5ecf7-108">[out] A pointer to a variable that receives the line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5ecf7-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="5ecf7-109">Return Value</span></span>  

 <span data-ttu-id="5ecf7-110">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="5ecf7-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ecf7-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5ecf7-111">See also</span></span>

- [<span data-ttu-id="5ecf7-112">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5ecf7-112">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
