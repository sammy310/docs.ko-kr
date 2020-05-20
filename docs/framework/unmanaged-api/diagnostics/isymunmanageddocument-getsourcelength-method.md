---
title: ISymUnmanagedDocument::GetSourceLength 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetSourceLength
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetSourceLength
helpviewer_keywords:
- GetSourceLength method [.NET Framework debugging]
- ISymUnmanagedDocument::GetSourceLength method [.NET Framework debugging]
ms.assetid: e087dbbb-f4fb-4fbe-8292-e4f1a14d0df2
topic_type:
- apiref
ms.openlocfilehash: e84639c1d63e6935b9b363f01c12bf0fbd3390e3
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615620"
---
# <a name="isymunmanageddocumentgetsourcelength-method"></a><span data-ttu-id="88683-102">ISymUnmanagedDocument::GetSourceLength 메서드</span><span class="sxs-lookup"><span data-stu-id="88683-102">ISymUnmanagedDocument::GetSourceLength Method</span></span>
<span data-ttu-id="88683-103">포함 리소스의 길이(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="88683-103">Gets the length, in bytes, of the embedded source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88683-104">구문</span><span class="sxs-lookup"><span data-stu-id="88683-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceLength(  
    [out, retval]  ULONG32*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="88683-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="88683-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="88683-106">제한이 포함 된 소스의 길이 (바이트)를 나타내는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="88683-106">[out] A pointer to a variable that indicates the length, in bytes, of the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="88683-107">Return Value</span><span class="sxs-lookup"><span data-stu-id="88683-107">Return Value</span></span>  
 <span data-ttu-id="88683-108">메서드가 성공 하면 S_OK 합니다.</span><span class="sxs-lookup"><span data-stu-id="88683-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88683-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="88683-109">See also</span></span>

- [<span data-ttu-id="88683-110">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="88683-110">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
