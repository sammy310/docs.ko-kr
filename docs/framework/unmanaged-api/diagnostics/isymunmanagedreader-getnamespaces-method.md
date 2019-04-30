---
title: ISymUnmanagedReader::GetNamespaces 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetNamespaces
helpviewer_keywords:
- ISymUnmanagedReader::GetNamespaces method [.NET Framework debugging]
- GetNamespaces method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 3feb4796-2fab-45ce-beca-6f5bc530b971
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 570532433483e9d0a08f4d685087c0736e135390
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993306"
---
# <a name="isymunmanagedreadergetnamespaces-method"></a><span data-ttu-id="d79f4-102">ISymUnmanagedReader::GetNamespaces 메서드</span><span class="sxs-lookup"><span data-stu-id="d79f4-102">ISymUnmanagedReader::GetNamespaces Method</span></span>
<span data-ttu-id="d79f4-103">이 기호 저장소 내의 전역 범위에서 정의 된 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d79f4-103">Gets the namespaces defined at global scope within this symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d79f4-104">구문</span><span class="sxs-lookup"><span data-stu-id="d79f4-104">Syntax</span></span>  
  
```  
HRESULT GetNamespaces (  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is (cNameSpaces),  
        length_is (*pcNameSpaces)]  
        ISymUnmanagedNamespace*  namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d79f4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d79f4-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="d79f4-106">[in] 네임 스페이스 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="d79f4-106">[in] The size of the namespaces array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="d79f4-107">[out] 네임 스페이스 목록 길이 수신 하는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d79f4-107">[out] A pointer to a variable that receives the length of the namespace list.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="d79f4-108">[out] 네임 스페이스 목록에서 받는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d79f4-108">[out] A pointer to a variable that receives the namespace list.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d79f4-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="d79f4-109">Return Value</span></span>  
 <span data-ttu-id="d79f4-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="d79f4-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d79f4-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d79f4-111">Requirements</span></span>  
 <span data-ttu-id="d79f4-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d79f4-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d79f4-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="d79f4-113">See also</span></span>

- [<span data-ttu-id="d79f4-114">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d79f4-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
