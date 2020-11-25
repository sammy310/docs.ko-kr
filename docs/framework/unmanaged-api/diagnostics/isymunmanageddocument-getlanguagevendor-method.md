---
title: ISymUnmanagedDocument::GetLanguageVendor 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetLanguageVendor
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetLanguageVendor
helpviewer_keywords:
- GetLanguageVendor method [.NET Framework debugging]
- ISymUnmanagedDocument::GetLanguageVendor method [.NET Framework debugging]
ms.assetid: 1d4b702e-4922-441d-8b44-03804284f70b
topic_type:
- apiref
ms.openlocfilehash: bac0f187409a191dda1ef635ec9b2da1aee25981
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700953"
---
# <a name="isymunmanageddocumentgetlanguagevendor-method"></a><span data-ttu-id="27066-102">ISymUnmanagedDocument::GetLanguageVendor 메서드</span><span class="sxs-lookup"><span data-stu-id="27066-102">ISymUnmanagedDocument::GetLanguageVendor Method</span></span>

<span data-ttu-id="27066-103">이 문서의 언어 공급 업체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="27066-103">Gets the language vendor of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27066-104">구문</span><span class="sxs-lookup"><span data-stu-id="27066-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLanguageVendor(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27066-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="27066-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="27066-106">제한이 언어 공급 업체를 받는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="27066-106">[out] A pointer to a variable that receives the language vendor.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="27066-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="27066-107">Return Value</span></span>  

 <span data-ttu-id="27066-108">메서드가 성공 하면 S_OK 합니다.</span><span class="sxs-lookup"><span data-stu-id="27066-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27066-109">참조</span><span class="sxs-lookup"><span data-stu-id="27066-109">See also</span></span>

- [<span data-ttu-id="27066-110">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="27066-110">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
