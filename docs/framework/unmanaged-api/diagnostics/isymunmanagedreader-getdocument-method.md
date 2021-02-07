---
description: '자세히 알아보기: ISymUnmanagedReader:: GetDocument 메서드'
title: ISymUnmanagedReader::GetDocument 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocument
helpviewer_keywords:
- ISymUnmanagedReader::GetDocument method [.NET Framework debugging]
- GetDocument method [.NET Framework debugging]
ms.assetid: bb203853-6a6d-4027-b9e9-603a7f28b9d3
topic_type:
- apiref
ms.openlocfilehash: 7f2f31467cfd00de68737224a2c1af5b1e78efed
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764101"
---
# <a name="isymunmanagedreadergetdocument-method"></a><span data-ttu-id="43990-103">ISymUnmanagedReader::GetDocument 메서드</span><span class="sxs-lookup"><span data-stu-id="43990-103">ISymUnmanagedReader::GetDocument Method</span></span>

<span data-ttu-id="43990-104">문서를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="43990-104">Finds a document.</span></span> <span data-ttu-id="43990-105">문서 언어, 공급 업체 및 형식은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="43990-105">The document language, vendor, and type are optional.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43990-106">구문</span><span class="sxs-lookup"><span data-stu-id="43990-106">Syntax</span></span>  
  
```cpp  
HRESULT GetDocument (  
    [in]  WCHAR  *url,  
    [in]  GUID   language,  
    [in]  GUID   languageVendor,  
    [in]  GUID   documentType,  
    [out, retval] ISymUnmanagedDocument** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43990-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="43990-107">Parameters</span></span>  

 `url`  
 <span data-ttu-id="43990-108">진행 문서를 식별 하는 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="43990-108">[in] The URL that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="43990-109">진행 문서 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="43990-109">[in] The document language.</span></span> <span data-ttu-id="43990-110">이 매개 변수는 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="43990-110">This parameter is optional.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="43990-111">진행 문서 언어의 공급 업체 id입니다.</span><span class="sxs-lookup"><span data-stu-id="43990-111">[in] The identity of the vendor for the document language.</span></span> <span data-ttu-id="43990-112">이 매개 변수는 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="43990-112">This parameter is optional.</span></span>  
  
 `documentType`  
 <span data-ttu-id="43990-113">진행 문서의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="43990-113">[in] The type of the document.</span></span> <span data-ttu-id="43990-114">이 매개 변수는 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="43990-114">This parameter is optional.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="43990-115">제한이 반환 된 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="43990-115">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="43990-116">Return Value</span><span class="sxs-lookup"><span data-stu-id="43990-116">Return Value</span></span>  

 <span data-ttu-id="43990-117">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="43990-117">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43990-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="43990-118">Requirements</span></span>  

 <span data-ttu-id="43990-119">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="43990-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43990-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="43990-120">See also</span></span>

- [<span data-ttu-id="43990-121">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="43990-121">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
