---
description: ISymUnmanagedWriter::D efineParameter 메서드에 대해 자세히 알아보세요.
title: ISymUnmanagedWriter::DefineParameter 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineParameter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineParameter
helpviewer_keywords:
- DefineParameter method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineParameter method [.NET Framework debugging]
ms.assetid: a8e3dd32-6a44-4371-9a74-f417b11998c8
topic_type:
- apiref
ms.openlocfilehash: 1e42140e33a99b224ccf3eff7ea29b7aa3ff1b15
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762359"
---
# <a name="isymunmanagedwriterdefineparameter-method"></a><span data-ttu-id="ee882-103">ISymUnmanagedWriter::DefineParameter 메서드</span><span class="sxs-lookup"><span data-stu-id="ee882-103">ISymUnmanagedWriter::DefineParameter Method</span></span>

<span data-ttu-id="ee882-104">현재 메서드의 단일 매개 변수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ee882-104">Defines a single parameter in the current method.</span></span> <span data-ttu-id="ee882-105">매개 변수 형식은 메서드의 시그니처 내에서 매개 변수의 위치 (시퀀스)에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ee882-105">The parameter type is taken from the parameter's position (sequence) within the method's signature.</span></span>  
  
 <span data-ttu-id="ee882-106">매개 변수가 지정 된 메서드에 대 한 메타 데이터에 정의 되어 있는 경우에는이 메서드를 사용 하 여 매개 변수를 다시 정의할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ee882-106">If parameters are defined in the metadata for a given method, you do not have to define them again by using this method.</span></span> <span data-ttu-id="ee882-107">기호 판독기는 기호 저장소를 확인 하기 전에 매개 변수에 대 한 일반 메타 데이터를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee882-107">The symbol readers must check the normal metadata for the parameters before checking the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee882-108">구문</span><span class="sxs-lookup"><span data-stu-id="ee882-108">Syntax</span></span>  
  
```cpp  
HRESULT DefineParameter(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      sequence,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee882-109">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ee882-109">Parameters</span></span>  

 `name`  
 <span data-ttu-id="ee882-110">진행 매개 변수 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ee882-110">[in] The parameter name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="ee882-111">진행 매개 변수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="ee882-111">[in] The parameter attributes.</span></span>  
  
 `sequence`  
 <span data-ttu-id="ee882-112">진행 매개 변수 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="ee882-112">[in] The parameter signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="ee882-113">진행 주소 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="ee882-113">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="ee882-114">진행 매개 변수 사양의 첫 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="ee882-114">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="ee882-115">진행 매개 변수 사양의 두 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="ee882-115">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="ee882-116">진행 매개 변수 사양의 세 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="ee882-116">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ee882-117">Return Value</span><span class="sxs-lookup"><span data-stu-id="ee882-117">Return Value</span></span>  

 <span data-ttu-id="ee882-118">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="ee882-118">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee882-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ee882-119">Requirements</span></span>  

 <span data-ttu-id="ee882-120">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="ee882-120">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee882-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ee882-121">See also</span></span>

- [<span data-ttu-id="ee882-122">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ee882-122">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
