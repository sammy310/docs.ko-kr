---
title: ISymUnmanagedReader::GetMethodByVersion 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodByVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodByVersion
helpviewer_keywords:
- ISymUnmanagedReader::GetMethodByVersion method [.NET Framework debugging]
- GetMethodByVersion method [.NET Framework debugging]
ms.assetid: 6ddb0631-4569-41b3-93e4-50fdfaa486dc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ebf2fea9f987818c93a1e865f2ed2ce33142050c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468665"
---
# <a name="isymunmanagedreadergetmethodbyversion-method"></a><span data-ttu-id="c3e99-102">ISymUnmanagedReader::GetMethodByVersion 메서드</span><span class="sxs-lookup"><span data-stu-id="c3e99-102">ISymUnmanagedReader::GetMethodByVersion Method</span></span>
<span data-ttu-id="c3e99-103">지정 된 메서드 토큰 및 편집 복사 버전 번호를 기호 판독기 메서드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c3e99-103">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span> <span data-ttu-id="c3e99-104">버전 번호는 1부터 시작 하 고 메서드를 편집 하 고 복사 작업의 결과로 변경 될 때마다 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3e99-104">Version numbers start at 1 and are incremented each time the method is changed as a result of an edit-and-copy operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3e99-105">구문</span><span class="sxs-lookup"><span data-stu-id="c3e99-105">Syntax</span></span>  
  
```  
HRESULT GetMethodByVersion (  
    [in]  mdMethodDef  token,  
    [in]  int  version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3e99-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c3e99-106">Parameters</span></span>  
 `token`  
 <span data-ttu-id="c3e99-107">[in] 메서드 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="c3e99-107">[in] The method token.</span></span>  
  
 `version`  
 <span data-ttu-id="c3e99-108">[in] 메서드 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="c3e99-108">[in] The method version.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="c3e99-109">[out] 반환 되는 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c3e99-109">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c3e99-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="c3e99-110">Return Value</span></span>  
 <span data-ttu-id="c3e99-111">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="c3e99-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3e99-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c3e99-112">Requirements</span></span>  
 <span data-ttu-id="c3e99-113">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c3e99-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3e99-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="c3e99-114">See also</span></span>
- [<span data-ttu-id="c3e99-115">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c3e99-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
