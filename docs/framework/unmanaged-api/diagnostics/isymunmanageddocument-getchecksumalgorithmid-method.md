---
description: '자세히 알아보기: ISymUnmanagedDocument:: GetCheckSumAlgorithmId 메서드'
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
ms.openlocfilehash: 835f56875a1adc3a3b6617a5a0b280f60f918236
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772122"
---
# <a name="isymunmanageddocumentgetchecksumalgorithmid-method"></a><span data-ttu-id="b25d4-103">ISymUnmanagedDocument::GetCheckSumAlgorithmId 메서드</span><span class="sxs-lookup"><span data-stu-id="b25d4-103">ISymUnmanagedDocument::GetCheckSumAlgorithmId Method</span></span>

<span data-ttu-id="b25d4-104">체크섬 알고리즘 식별자를 가져오거나, 체크섬이 없을 경우 모든 0의 GUID를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b25d4-104">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b25d4-105">구문</span><span class="sxs-lookup"><span data-stu-id="b25d4-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCheckSumAlgorithmId(  
    [out, retval] GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b25d4-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b25d4-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="b25d4-107">제한이 체크섬 알고리즘 식별자를 받는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b25d4-107">[out] A pointer to a variable that receives the checksum algorithm identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b25d4-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="b25d4-108">Return Value</span></span>  

 <span data-ttu-id="b25d4-109">메서드가 성공 하면 S_OK 합니다.</span><span class="sxs-lookup"><span data-stu-id="b25d4-109">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b25d4-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b25d4-110">See also</span></span>

- [<span data-ttu-id="b25d4-111">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b25d4-111">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
