---
description: '자세히 알아보기: ICLRDebuggingLibraryProvider 인터페이스'
title: ICLRDebuggingLibraryProvider 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRDebuggingLibraryProvider
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebuggingLibraryProvider
helpviewer_keywords:
- ICLRDebuggingLibraryProvider interface [.NET Framework debugging]
ms.assetid: 67739617-6add-41a9-9de5-a3200c3109ce
topic_type:
- apiref
ms.openlocfilehash: 8aaec87e97d45c8b7b6f87aee64154ea3f48b133
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99723285"
---
# <a name="iclrdebugginglibraryprovider-interface"></a><span data-ttu-id="5485b-103">ICLRDebuggingLibraryProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5485b-103">ICLRDebuggingLibraryProvider Interface</span></span>

<span data-ttu-id="5485b-104">요청 시 공용 언어 런타임 버전별 디버깅 라이브러리를 찾고 로드 하는 데 사용할 수 있는 라이브러리 공급자 콜백 인터페이스를 가져오는 [ProvideLibrary method](iclrdebugginglibraryprovider-providelibrary-method.md) 메서드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="5485b-104">Includes the [ProvideLibrary Method](iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5485b-105">메서드</span><span class="sxs-lookup"><span data-stu-id="5485b-105">Methods</span></span>  
  
|<span data-ttu-id="5485b-106">메서드</span><span class="sxs-lookup"><span data-stu-id="5485b-106">Method</span></span>|<span data-ttu-id="5485b-107">설명</span><span class="sxs-lookup"><span data-stu-id="5485b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5485b-108">ProvideLibrary 메서드</span><span class="sxs-lookup"><span data-stu-id="5485b-108">ProvideLibrary Method</span></span>](iclrdebugginglibraryprovider-providelibrary-method.md)|<span data-ttu-id="5485b-109">디버거가 디버그 라이브러리를 로드 하는 데 사용할 수 있는 모듈에 대 한 핸들을 제공할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5485b-109">Allows the debugger to provide a handle to a module which can be used to load a debug library.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5485b-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5485b-110">Requirements</span></span>  

 <span data-ttu-id="5485b-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5485b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5485b-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5485b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5485b-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5485b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5485b-114">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5485b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5485b-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5485b-115">See also</span></span>

- [<span data-ttu-id="5485b-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5485b-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="5485b-117">디버깅</span><span class="sxs-lookup"><span data-stu-id="5485b-117">Debugging</span></span>](index.md)
