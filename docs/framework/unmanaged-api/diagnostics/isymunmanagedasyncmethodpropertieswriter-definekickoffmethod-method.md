---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod 메서드
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
ms.openlocfilehash: c35455fc679d79d56814a9c2f026ec395e944f24
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441723"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="37411-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="37411-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="37411-103">비동기 작업을 시작 하는 시작 메서드를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="37411-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37411-104">구문</span><span class="sxs-lookup"><span data-stu-id="37411-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37411-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="37411-105">Parameters</span></span>  
  
|<span data-ttu-id="37411-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="37411-106">Parameter</span></span>|<span data-ttu-id="37411-107">설명</span><span class="sxs-lookup"><span data-stu-id="37411-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="37411-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="37411-108">Return Value</span></span>  
 <span data-ttu-id="37411-109">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="37411-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37411-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="37411-110">Requirements</span></span>  
 <span data-ttu-id="37411-111">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="37411-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37411-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="37411-112">See also</span></span>

- [<span data-ttu-id="37411-113">ISymUnmanagedAsyncMethodPropertiesWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="37411-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)
