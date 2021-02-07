---
description: '자세히 알아보기: ISymUnmanagedDocument:: GetLanguageVendor 메서드'
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
ms.openlocfilehash: 247c6c24f57211b3b46ad773d8e77d7e0f16fd01
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710246"
---
# <a name="isymunmanageddocumentgetlanguagevendor-method"></a><span data-ttu-id="a4bb1-103">ISymUnmanagedDocument::GetLanguageVendor 메서드</span><span class="sxs-lookup"><span data-stu-id="a4bb1-103">ISymUnmanagedDocument::GetLanguageVendor Method</span></span>

<span data-ttu-id="a4bb1-104">이 문서의 언어 공급 업체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a4bb1-104">Gets the language vendor of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4bb1-105">구문</span><span class="sxs-lookup"><span data-stu-id="a4bb1-105">Syntax</span></span>  
  
```cpp  
HRESULT GetLanguageVendor(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4bb1-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a4bb1-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="a4bb1-107">제한이 언어 공급 업체를 받는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a4bb1-107">[out] A pointer to a variable that receives the language vendor.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a4bb1-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="a4bb1-108">Return Value</span></span>  

 <span data-ttu-id="a4bb1-109">메서드가 성공 하면 S_OK 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4bb1-109">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4bb1-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a4bb1-110">See also</span></span>

- [<span data-ttu-id="a4bb1-111">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a4bb1-111">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
