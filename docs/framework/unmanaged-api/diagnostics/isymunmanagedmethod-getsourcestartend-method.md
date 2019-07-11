---
title: ISymUnmanagedMethod::GetSourceStartEnd 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetSourceStartEnd
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSourceStartEnd
helpviewer_keywords:
- GetSourceStartEnd method [.NET Framework debugging]
- ISymUnmanagedMethod::GetSourceStartEnd method [.NET Framework debugging]
ms.assetid: 2a420900-01f1-4461-8777-3a34a6dc1426
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a75fed4c46ea7e31177ac0446c8fae7805535323
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759432"
---
# <a name="isymunmanagedmethodgetsourcestartend-method"></a><span data-ttu-id="7ea03-102">ISymUnmanagedMethod::GetSourceStartEnd 메서드</span><span class="sxs-lookup"><span data-stu-id="7ea03-102">ISymUnmanagedMethod::GetSourceStartEnd Method</span></span>
<span data-ttu-id="7ea03-103">이 메서드의 원본에 대 한 시작 및 끝 문서 위치를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7ea03-103">Gets the start and end document positions for the source of this method.</span></span> <span data-ttu-id="7ea03-104">첫 번째 배열 위치 시작 이며 두 번째 배열 위치 끝입니다.</span><span class="sxs-lookup"><span data-stu-id="7ea03-104">The first array position is the start, and the second array position is the end.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ea03-105">구문</span><span class="sxs-lookup"><span data-stu-id="7ea03-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceStartEnd(  
    [in]  ISymUnmanagedDocument  *docs[2],  
    [in]  ULONG32                lines[2],  
    [in]  ULONG32                columns[2],  
    [out] BOOL                   *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ea03-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7ea03-106">Parameters</span></span>  
 `docs`  
 <span data-ttu-id="7ea03-107">[in] 시작 및 종료 소스 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="7ea03-107">[in] The starting and ending source documents.</span></span>  
  
 `lines`  
 <span data-ttu-id="7ea03-108">[in] 소스 문서의 시작 및 해당 줄을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ea03-108">[in] The starting and ending lines in the corresponding source documents.</span></span>  
  
 `columns`  
 <span data-ttu-id="7ea03-109">[in] 소스 문서의 시작 및 해당 열을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ea03-109">[in] The starting and ending columns in the corresponding source documents.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="7ea03-110">[out] `true` 위치 고, 그렇지 않으면 정의 된 경우 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="7ea03-110">[out] `true` if positions were defined; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7ea03-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="7ea03-111">Return Value</span></span>  
 <span data-ttu-id="7ea03-112">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="7ea03-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ea03-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7ea03-113">Requirements</span></span>  
 <span data-ttu-id="7ea03-114">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7ea03-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ea03-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="7ea03-115">See also</span></span>

- [<span data-ttu-id="7ea03-116">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7ea03-116">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
