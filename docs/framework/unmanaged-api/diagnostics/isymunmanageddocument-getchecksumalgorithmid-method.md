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
ms.openlocfilehash: f2df98728eec28ffca05b2e246575fc5c882a078
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939883"
---
# <a name="isymunmanageddocumentgetchecksumalgorithmid-method"></a><span data-ttu-id="74c12-102">ISymUnmanagedDocument::GetCheckSumAlgorithmId 메서드</span><span class="sxs-lookup"><span data-stu-id="74c12-102">ISymUnmanagedDocument::GetCheckSumAlgorithmId Method</span></span>
<span data-ttu-id="74c12-103">체크섬 알고리즘 식별자를 가져오거나 체크섬이 없는 경우에 모두 0으로 GUID를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="74c12-103">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74c12-104">구문</span><span class="sxs-lookup"><span data-stu-id="74c12-104">Syntax</span></span>  
  
```  
HRESULT GetCheckSumAlgorithmId(  
    [out, retval] GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74c12-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="74c12-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="74c12-106">[out] 체크섬 알고리즘 식별자를 수신 하는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="74c12-106">[out] A pointer to a variable that receives the checksum algorithm identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="74c12-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="74c12-107">Return Value</span></span>  
 <span data-ttu-id="74c12-108">메서드가 성공 하면 S_OK입니다.</span><span class="sxs-lookup"><span data-stu-id="74c12-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74c12-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="74c12-109">See also</span></span>

- [<span data-ttu-id="74c12-110">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="74c12-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
