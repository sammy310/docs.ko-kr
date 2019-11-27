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
ms.openlocfilehash: 01ab69b73a7bc4929e2ebd49b3847f8d7c4646a2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448871"
---
# <a name="isymunmanagedmethodgetsourcestartend-method"></a><span data-ttu-id="7c99c-102">ISymUnmanagedMethod::GetSourceStartEnd 메서드</span><span class="sxs-lookup"><span data-stu-id="7c99c-102">ISymUnmanagedMethod::GetSourceStartEnd Method</span></span>
<span data-ttu-id="7c99c-103">이 메서드의 소스에 대 한 시작 및 끝 문서 위치를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7c99c-103">Gets the start and end document positions for the source of this method.</span></span> <span data-ttu-id="7c99c-104">첫 번째 배열 위치는 시작이 고 두 번째 배열 위치는 끝입니다.</span><span class="sxs-lookup"><span data-stu-id="7c99c-104">The first array position is the start, and the second array position is the end.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c99c-105">구문</span><span class="sxs-lookup"><span data-stu-id="7c99c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceStartEnd(  
    [in]  ISymUnmanagedDocument  *docs[2],  
    [in]  ULONG32                lines[2],  
    [in]  ULONG32                columns[2],  
    [out] BOOL                   *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c99c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7c99c-106">Parameters</span></span>  
 `docs`  
 <span data-ttu-id="7c99c-107">진행 시작 및 종료 소스 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="7c99c-107">[in] The starting and ending source documents.</span></span>  
  
 `lines`  
 <span data-ttu-id="7c99c-108">진행 해당 소스 문서의 시작 및 종료 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="7c99c-108">[in] The starting and ending lines in the corresponding source documents.</span></span>  
  
 `columns`  
 <span data-ttu-id="7c99c-109">진행 해당 소스 문서의 시작 및 끝 열입니다.</span><span class="sxs-lookup"><span data-stu-id="7c99c-109">[in] The starting and ending columns in the corresponding source documents.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="7c99c-110">[out] 위치가 정의 된 경우 `true` 합니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="7c99c-110">[out] `true` if positions were defined; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7c99c-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="7c99c-111">Return Value</span></span>  
 <span data-ttu-id="7c99c-112">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="7c99c-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c99c-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7c99c-113">Requirements</span></span>  
 <span data-ttu-id="7c99c-114">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="7c99c-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c99c-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7c99c-115">See also</span></span>

- [<span data-ttu-id="7c99c-116">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7c99c-116">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
