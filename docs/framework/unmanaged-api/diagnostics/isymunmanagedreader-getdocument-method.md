---
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
ms.openlocfilehash: 1fcb885b6e19457065c2ca9971f068b42f97147d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448351"
---
# <a name="isymunmanagedreadergetdocument-method"></a><span data-ttu-id="873c8-102">ISymUnmanagedReader::GetDocument 메서드</span><span class="sxs-lookup"><span data-stu-id="873c8-102">ISymUnmanagedReader::GetDocument Method</span></span>
<span data-ttu-id="873c8-103">문서를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="873c8-103">Finds a document.</span></span> <span data-ttu-id="873c8-104">문서 언어, 공급 업체 및 형식은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="873c8-104">The document language, vendor, and type are optional.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="873c8-105">구문</span><span class="sxs-lookup"><span data-stu-id="873c8-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDocument (  
    [in]  WCHAR  *url,  
    [in]  GUID   language,  
    [in]  GUID   languageVendor,  
    [in]  GUID   documentType,  
    [out, retval] ISymUnmanagedDocument** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="873c8-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="873c8-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="873c8-107">진행 문서를 식별 하는 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="873c8-107">[in] The URL that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="873c8-108">진행 문서 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="873c8-108">[in] The document language.</span></span> <span data-ttu-id="873c8-109">이 매개 변수는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="873c8-109">This parameter is optional.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="873c8-110">진행 문서 언어의 공급 업체 id입니다.</span><span class="sxs-lookup"><span data-stu-id="873c8-110">[in] The identity of the vendor for the document language.</span></span> <span data-ttu-id="873c8-111">이 매개 변수는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="873c8-111">This parameter is optional.</span></span>  
  
 `documentType`  
 <span data-ttu-id="873c8-112">진행 문서의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="873c8-112">[in] The type of the document.</span></span> <span data-ttu-id="873c8-113">이 매개 변수는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="873c8-113">This parameter is optional.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="873c8-114">제한이 반환 된 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="873c8-114">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="873c8-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="873c8-115">Return Value</span></span>  
 <span data-ttu-id="873c8-116">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="873c8-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="873c8-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="873c8-117">Requirements</span></span>  
 <span data-ttu-id="873c8-118">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="873c8-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="873c8-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="873c8-119">See also</span></span>

- [<span data-ttu-id="873c8-120">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="873c8-120">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
