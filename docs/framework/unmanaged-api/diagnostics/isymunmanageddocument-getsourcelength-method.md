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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2717a279abf7fb1b704a769d54654d97949cc0a2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939868"
---
# <a name="isymunmanageddocumentgetsourcelength-method"></a><span data-ttu-id="e8678-102">ISymUnmanagedDocument::GetSourceLength 메서드</span><span class="sxs-lookup"><span data-stu-id="e8678-102">ISymUnmanagedDocument::GetSourceLength Method</span></span>
<span data-ttu-id="e8678-103">포함 소스의 길이(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e8678-103">Gets the length, in bytes, of the embedded source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8678-104">구문</span><span class="sxs-lookup"><span data-stu-id="e8678-104">Syntax</span></span>  
  
```  
HRESULT GetSourceLength(  
    [out, retval]  ULONG32*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8678-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e8678-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="e8678-106">[out] 포함 소스의 길이 (바이트)를 지정 하는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e8678-106">[out] A pointer to a variable that indicates the length, in bytes, of the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e8678-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="e8678-107">Return Value</span></span>  
 <span data-ttu-id="e8678-108">메서드가 성공 하면 S_OK입니다.</span><span class="sxs-lookup"><span data-stu-id="e8678-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8678-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="e8678-109">See also</span></span>

- [<span data-ttu-id="e8678-110">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e8678-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
