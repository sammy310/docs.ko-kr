---
description: '자세히 알아보기: ISymUnmanagedSymbolSearchInfo:: GetHRESULT 메서드'
title: ISymUnmanagedSymbolSearchInfo::GetHRESULT 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetHRESULT
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetHRESULT
helpviewer_keywords:
- ISymUnmanagedSymbolSearchInfo::GetHRESULT method [.NET Framework debugging]
- GetHRESULT method [.NET Framework debugging]
ms.assetid: 6999dc3d-65d7-4bf6-bb0a-6efc0fc72588
topic_type:
- apiref
ms.openlocfilehash: 5d351d84ba4e91ccb9acb531e77407a2d1caceec
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763113"
---
# <a name="isymunmanagedsymbolsearchinfogethresult-method"></a><span data-ttu-id="90304-103">ISymUnmanagedSymbolSearchInfo::GetHRESULT 메서드</span><span class="sxs-lookup"><span data-stu-id="90304-103">ISymUnmanagedSymbolSearchInfo::GetHRESULT Method</span></span>

<span data-ttu-id="90304-104">HRESULT를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="90304-104">Gets the HRESULT.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90304-105">구문</span><span class="sxs-lookup"><span data-stu-id="90304-105">Syntax</span></span>  
  
```cpp  
HRESULT GetHRESULT(  
    [out] HRESULT *phr);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90304-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="90304-106">Parameters</span></span>  

 `phr`  
 <span data-ttu-id="90304-107">제한이 HRESULT에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="90304-107">[out] A pointer to the HRESULT.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="90304-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="90304-108">Return Value</span></span>  

 <span data-ttu-id="90304-109">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="90304-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90304-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="90304-110">Requirements</span></span>  

 <span data-ttu-id="90304-111">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="90304-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90304-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="90304-112">See also</span></span>

- [<span data-ttu-id="90304-113">ISymUnmanagedSymbolSearchInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="90304-113">ISymUnmanagedSymbolSearchInfo Interface</span></span>](isymunmanagedsymbolsearchinfo-interface.md)
