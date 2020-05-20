---
title: ISymUnmanagedDocument::GetURL 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetURL
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetURL
helpviewer_keywords:
- GetURL method [.NET Framework debugging]
- ISymUnmanagedDocument::GetURL method [.NET Framework debugging]
ms.assetid: 60600178-c2b5-4cab-b3a5-f0f61acebaf1
topic_type:
- apiref
ms.openlocfilehash: 3685707f1983ffec413e9cea2df5034ac53f643a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615594"
---
# <a name="isymunmanageddocumentgeturl-method"></a><span data-ttu-id="3748e-102">ISymUnmanagedDocument::GetURL 메서드</span><span class="sxs-lookup"><span data-stu-id="3748e-102">ISymUnmanagedDocument::GetURL Method</span></span>
<span data-ttu-id="3748e-103">이 문서에 대 한 URL (uniform resource locator)을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748e-103">Returns the uniform resource locator (URL) for this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3748e-104">구문</span><span class="sxs-lookup"><span data-stu-id="3748e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetURL(  
    [in]  ULONG32  cchUrl,  
    [out] ULONG32  *pcchUrl,  
    [out, size_is(cchUrl), length_is(*pcchUrl)] WCHAR szUrl[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3748e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3748e-105">Parameters</span></span>  
 `cchUrl`  
 <span data-ttu-id="3748e-106">진행 버퍼의 크기 (문자) `szURL` 입니다.</span><span class="sxs-lookup"><span data-stu-id="3748e-106">[in] The size, in characters, of the `szURL` buffer.</span></span>  
  
 `pcchUrl`  
 <span data-ttu-id="3748e-107">제한이 Null 종료를 포함 하 여 URL의 크기를 받는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3748e-107">[out] A pointer to a variable that receives the size of the URL, including the null termination.</span></span>  
  
 `szUrl`  
 <span data-ttu-id="3748e-108">제한이 URL을 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="3748e-108">[out] The buffer containing the URL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3748e-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="3748e-109">Return Value</span></span>  
 <span data-ttu-id="3748e-110">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="3748e-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3748e-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3748e-111">See also</span></span>

- [<span data-ttu-id="3748e-112">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3748e-112">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
