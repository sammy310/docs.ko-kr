---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod 메서드
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
ms.openlocfilehash: 418a77855d1cb34a07f5957059b5a6f5a106c321
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707089"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="cd8e6-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="cd8e6-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>

<span data-ttu-id="cd8e6-103">비동기 작업을 시작 하는 시작 메서드를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd8e6-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd8e6-104">구문</span><span class="sxs-lookup"><span data-stu-id="cd8e6-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd8e6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cd8e6-105">Parameters</span></span>  
  
|<span data-ttu-id="cd8e6-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cd8e6-106">Parameter</span></span>|<span data-ttu-id="cd8e6-107">설명</span><span class="sxs-lookup"><span data-stu-id="cd8e6-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="cd8e6-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="cd8e6-108">Return Value</span></span>  

 <span data-ttu-id="cd8e6-109">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="cd8e6-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd8e6-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cd8e6-110">Requirements</span></span>  

 <span data-ttu-id="cd8e6-111">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="cd8e6-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd8e6-112">참조</span><span class="sxs-lookup"><span data-stu-id="cd8e6-112">See also</span></span>

- [<span data-ttu-id="cd8e6-113">ISymUnmanagedAsyncMethodPropertiesWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cd8e6-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)
