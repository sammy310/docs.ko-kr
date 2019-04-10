---
title: ISymUnmanagedWriter::SetUserEntryPoint 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetUserEntryPoint
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetUserEntryPoint
helpviewer_keywords:
- ISymUnmanagedWriter::SetUserEntryPoint method [.NET Framework debugging]
- SetUserEntryPoint method [.NET Framework debugging]
ms.assetid: d4dcc575-3ac8-4453-9be1-2b24f47363d7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d14d542a8c1d8adeaf56dc1564e8e10121cd4064
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59224223"
---
# <a name="isymunmanagedwritersetuserentrypoint-method"></a><span data-ttu-id="83d2b-102">ISymUnmanagedWriter::SetUserEntryPoint 메서드</span><span class="sxs-lookup"><span data-stu-id="83d2b-102">ISymUnmanagedWriter::SetUserEntryPoint Method</span></span>
<span data-ttu-id="83d2b-103">이 모듈에 대 한 진입점을 되는 사용자 정의 메서드를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="83d2b-103">Specifies the user-defined method that is the entry point for this module.</span></span> <span data-ttu-id="83d2b-104">예를 들어이 진입점에는 main 전에 컴파일러에서 생성 된 스텁이 대신 사용자의 기본 메서드 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83d2b-104">For example, this entry point could be the user's main method instead of compiler-generated stubs before main.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83d2b-105">구문</span><span class="sxs-lookup"><span data-stu-id="83d2b-105">Syntax</span></span>  
  
```  
HRESULT SetUserEntryPoint(  
    [in] mdMethodDef entryMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83d2b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="83d2b-106">Parameters</span></span>  
 `entryMethod`  
 <span data-ttu-id="83d2b-107">[in] 사용자 진입점인 메서드의 메타 데이터 토큰을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="83d2b-107">[in] The metadata token for the method that is the user entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="83d2b-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="83d2b-108">Return Value</span></span>  
 <span data-ttu-id="83d2b-109">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="83d2b-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83d2b-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="83d2b-110">Requirements</span></span>  
 <span data-ttu-id="83d2b-111">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="83d2b-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83d2b-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="83d2b-112">See also</span></span>

- [<span data-ttu-id="83d2b-113">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="83d2b-113">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
