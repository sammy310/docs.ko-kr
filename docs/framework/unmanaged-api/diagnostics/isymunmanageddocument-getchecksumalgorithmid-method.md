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
ms.openlocfilehash: 2bc673d2e331cd32d5317cb20f9418eb3a3b144a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431073"
---
# <a name="isymunmanageddocumentgetchecksumalgorithmid-method"></a><span data-ttu-id="8a7a5-102">ISymUnmanagedDocument::GetCheckSumAlgorithmId 메서드</span><span class="sxs-lookup"><span data-stu-id="8a7a5-102">ISymUnmanagedDocument::GetCheckSumAlgorithmId Method</span></span>
<span data-ttu-id="8a7a5-103">체크섬 알고리즘 식별자를 가져오거나, 체크섬이 없을 경우 모든 0의 GUID를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a7a5-103">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a7a5-104">구문</span><span class="sxs-lookup"><span data-stu-id="8a7a5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCheckSumAlgorithmId(  
    [out, retval] GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a7a5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8a7a5-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="8a7a5-106">제한이 체크섬 알고리즘 식별자를 받는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8a7a5-106">[out] A pointer to a variable that receives the checksum algorithm identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8a7a5-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="8a7a5-107">Return Value</span></span>  
 <span data-ttu-id="8a7a5-108">메서드가 성공 하면 S_OK 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a7a5-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a7a5-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8a7a5-109">See also</span></span>

- [<span data-ttu-id="8a7a5-110">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8a7a5-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
