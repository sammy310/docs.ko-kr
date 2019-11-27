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
ms.openlocfilehash: 458faedea418e626a6494ca2afcdbf0e034472e8
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447740"
---
# <a name="isymunmanagedreadergetnamespaces-method"></a><span data-ttu-id="404d4-102">ISymUnmanagedReader::GetNamespaces 메서드</span><span class="sxs-lookup"><span data-stu-id="404d4-102">ISymUnmanagedReader::GetNamespaces Method</span></span>
<span data-ttu-id="404d4-103">이 기호 저장소의 전역 범위에서 정의 된 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="404d4-103">Gets the namespaces defined at global scope within this symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="404d4-104">구문</span><span class="sxs-lookup"><span data-stu-id="404d4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespaces (  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is (cNameSpaces),  
        length_is (*pcNameSpaces)]  
        ISymUnmanagedNamespace*  namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="404d4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="404d4-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="404d4-106">진행 네임 스페이스 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="404d4-106">[in] The size of the namespaces array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="404d4-107">제한이 네임 스페이스 목록의 길이를 받는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="404d4-107">[out] A pointer to a variable that receives the length of the namespace list.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="404d4-108">제한이 네임 스페이스 목록을 받는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="404d4-108">[out] A pointer to a variable that receives the namespace list.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="404d4-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="404d4-109">Return Value</span></span>  
 <span data-ttu-id="404d4-110">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="404d4-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="404d4-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="404d4-111">Requirements</span></span>  
 <span data-ttu-id="404d4-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="404d4-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="404d4-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="404d4-113">See also</span></span>

- [<span data-ttu-id="404d4-114">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="404d4-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
