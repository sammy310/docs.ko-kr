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
ms.openlocfilehash: 3c82cf45bca3cc9ec73255586db73a903edaf1ef
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698574"
---
# <a name="isymunmanageddocumentgetchecksumalgorithmid-method"></a><span data-ttu-id="a7eda-102">ISymUnmanagedDocument::GetCheckSumAlgorithmId 메서드</span><span class="sxs-lookup"><span data-stu-id="a7eda-102">ISymUnmanagedDocument::GetCheckSumAlgorithmId Method</span></span>

<span data-ttu-id="a7eda-103">체크섬 알고리즘 식별자를 가져오거나, 체크섬이 없을 경우 모든 0의 GUID를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7eda-103">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7eda-104">구문</span><span class="sxs-lookup"><span data-stu-id="a7eda-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCheckSumAlgorithmId(  
    [out, retval] GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7eda-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a7eda-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="a7eda-106">제한이 체크섬 알고리즘 식별자를 받는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a7eda-106">[out] A pointer to a variable that receives the checksum algorithm identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a7eda-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="a7eda-107">Return Value</span></span>  

 <span data-ttu-id="a7eda-108">메서드가 성공 하면 S_OK 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7eda-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7eda-109">참조</span><span class="sxs-lookup"><span data-stu-id="a7eda-109">See also</span></span>

- [<span data-ttu-id="a7eda-110">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a7eda-110">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
