---
description: '자세히 알아보기: ISymUnmanagedDocument:: GetURL 메서드'
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
ms.openlocfilehash: b39b36054d80f9ad2f9dd076e2055ccbc6526973
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710194"
---
# <a name="isymunmanageddocumentgeturl-method"></a><span data-ttu-id="75704-103">ISymUnmanagedDocument::GetURL 메서드</span><span class="sxs-lookup"><span data-stu-id="75704-103">ISymUnmanagedDocument::GetURL Method</span></span>

<span data-ttu-id="75704-104">이 문서에 대 한 URL (uniform resource locator)을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="75704-104">Returns the uniform resource locator (URL) for this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75704-105">구문</span><span class="sxs-lookup"><span data-stu-id="75704-105">Syntax</span></span>  
  
```cpp  
HRESULT GetURL(  
    [in]  ULONG32  cchUrl,  
    [out] ULONG32  *pcchUrl,  
    [out, size_is(cchUrl), length_is(*pcchUrl)] WCHAR szUrl[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="75704-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="75704-106">Parameters</span></span>  

 `cchUrl`  
 <span data-ttu-id="75704-107">진행 버퍼의 크기 (문자) `szURL` 입니다.</span><span class="sxs-lookup"><span data-stu-id="75704-107">[in] The size, in characters, of the `szURL` buffer.</span></span>  
  
 `pcchUrl`  
 <span data-ttu-id="75704-108">제한이 Null 종료를 포함 하 여 URL의 크기를 받는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="75704-108">[out] A pointer to a variable that receives the size of the URL, including the null termination.</span></span>  
  
 `szUrl`  
 <span data-ttu-id="75704-109">제한이 URL을 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="75704-109">[out] The buffer containing the URL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="75704-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="75704-110">Return Value</span></span>  

 <span data-ttu-id="75704-111">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="75704-111">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75704-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="75704-112">See also</span></span>

- [<span data-ttu-id="75704-113">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="75704-113">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
