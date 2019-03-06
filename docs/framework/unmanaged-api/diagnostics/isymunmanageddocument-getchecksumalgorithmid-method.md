---
title: ISymUnmanagedDocument::GetCheckSumAlgorithmId 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetCheckSumAlgorithmId
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetCheckSumAlgorithmId
helpviewer_keywords:
- ISymUnmanagedDocument::GetCheckSumAlgorithmId method [.NET Framework debugging]
- GetCheckSumAlgorithmId method [.NET Framework debugging]
ms.assetid: c7f941cd-e25b-4b85-b1ce-5f77c9208fa9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 116792c6a669f31b0c69dcc0b25134af7e72f9f2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501034"
---
# <a name="isymunmanageddocumentgetchecksumalgorithmid-method"></a><span data-ttu-id="3eacc-102">ISymUnmanagedDocument::GetCheckSumAlgorithmId 메서드</span><span class="sxs-lookup"><span data-stu-id="3eacc-102">ISymUnmanagedDocument::GetCheckSumAlgorithmId Method</span></span>
<span data-ttu-id="3eacc-103">체크섬 알고리즘 식별자를 가져오거나 체크섬이 없는 경우에 모두 0으로 GUID를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3eacc-103">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3eacc-104">구문</span><span class="sxs-lookup"><span data-stu-id="3eacc-104">Syntax</span></span>  
  
```  
HRESULT GetCheckSumAlgorithmId(  
    [out, retval] GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3eacc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3eacc-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="3eacc-106">[out] 체크섬 알고리즘 식별자를 수신 하는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3eacc-106">[out] A pointer to a variable that receives the checksum algorithm identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3eacc-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="3eacc-107">Return Value</span></span>  
 <span data-ttu-id="3eacc-108">메서드가 성공 하면 S_OK입니다.</span><span class="sxs-lookup"><span data-stu-id="3eacc-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3eacc-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="3eacc-109">See also</span></span>
- [<span data-ttu-id="3eacc-110">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3eacc-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
