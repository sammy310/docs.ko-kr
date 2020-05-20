---
title: ISymUnmanagedWriter2::DefineGlobalVariable2 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineGlobalVariable2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineGlobalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineGlobalVariable2 method [.NET Framework debugging]
- DefineGlobalVariable2 method [.NET Framework debugging]
ms.assetid: 04d569d6-a151-4957-9872-f3f694c3e4a9
topic_type:
- apiref
ms.openlocfilehash: ed3c841c34b71b30f740117899353aa289e478d5
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614710"
---
# <a name="isymunmanagedwriter2defineglobalvariable2-method"></a><span data-ttu-id="d55a5-102">ISymUnmanagedWriter2::DefineGlobalVariable2 메서드</span><span class="sxs-lookup"><span data-stu-id="d55a5-102">ISymUnmanagedWriter2::DefineGlobalVariable2 Method</span></span>
<span data-ttu-id="d55a5-103">단일 전역 변수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d55a5-103">Defines a single global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d55a5-104">구문</span><span class="sxs-lookup"><span data-stu-id="d55a5-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineGlobalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d55a5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d55a5-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="d55a5-106">진행 전역 변수 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d55a5-106">[in] The global variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="d55a5-107">진행 전역 변수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d55a5-107">[in] The global variable attributes.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="d55a5-108">진행 시그니처의 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="d55a5-108">[in] The metadata token of the signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="d55a5-109">진행 주소 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="d55a5-109">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="d55a5-110">진행 매개 변수 사양의 첫 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d55a5-110">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="d55a5-111">진행 매개 변수 사양의 두 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d55a5-111">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="d55a5-112">진행 매개 변수 사양의 세 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d55a5-112">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d55a5-113">Return Value</span><span class="sxs-lookup"><span data-stu-id="d55a5-113">Return Value</span></span>  
 <span data-ttu-id="d55a5-114">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="d55a5-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d55a5-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d55a5-115">Requirements</span></span>  
 <span data-ttu-id="d55a5-116">**헤더:** CorSym</span><span class="sxs-lookup"><span data-stu-id="d55a5-116">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d55a5-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d55a5-117">See also</span></span>

- [<span data-ttu-id="d55a5-118">ISymUnmanagedWriter2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d55a5-118">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="d55a5-119">DefineGlobalVariable 메서드</span><span class="sxs-lookup"><span data-stu-id="d55a5-119">DefineGlobalVariable Method</span></span>](isymunmanagedwriter-defineglobalvariable-method.md)
