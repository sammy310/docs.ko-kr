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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 15b42bb72975fad4c1830a961f83d9e3065d055b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59187462"
---
# <a name="isymunmanageddocumentgeturl-method"></a><span data-ttu-id="df420-102">ISymUnmanagedDocument::GetURL 메서드</span><span class="sxs-lookup"><span data-stu-id="df420-102">ISymUnmanagedDocument::GetURL Method</span></span>
<span data-ttu-id="df420-103">이 문서에 대 한 uniform resource locator (URL)을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="df420-103">Returns the uniform resource locator (URL) for this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df420-104">구문</span><span class="sxs-lookup"><span data-stu-id="df420-104">Syntax</span></span>  
  
```  
HRESULT GetURL(  
    [in]  ULONG32  cchUrl,  
    [out] ULONG32  *pcchUrl,  
    [out, size_is(cchUrl), length_is(*pcchUrl)] WCHAR szUrl[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df420-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="df420-105">Parameters</span></span>  
 `cchUrl`  
 <span data-ttu-id="df420-106">[in] 문자에서 크기의는 `szURL` 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="df420-106">[in] The size, in characters, of the `szURL` buffer.</span></span>  
  
 `pcchUrl`  
 <span data-ttu-id="df420-107">[out] 변수는 null 종결을 포함 하 여 URL의 크기를 받는 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="df420-107">[out] A pointer to a variable that receives the size of the URL, including the null termination.</span></span>  
  
 `szUrl`  
 <span data-ttu-id="df420-108">[out] URL이 포함 된 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="df420-108">[out] The buffer containing the URL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df420-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="df420-109">Return Value</span></span>  
 <span data-ttu-id="df420-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="df420-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df420-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="df420-111">See also</span></span>

- [<span data-ttu-id="df420-112">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="df420-112">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
