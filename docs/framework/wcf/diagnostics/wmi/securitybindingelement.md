---
description: '자세히 알아보기: SecurityBindingElement'
title: SecurityBindingElement
ms.date: 03/30/2017
ms.assetid: ef93b6e6-3524-48a8-94d3-c8837f1872f9
ms.openlocfilehash: bc9a519978a9cccccd80a58abb8d109fa9bc9337
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99743813"
---
# <a name="securitybindingelement"></a><span data-ttu-id="9bbd3-103">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="9bbd3-103">SecurityBindingElement</span></span>

<span data-ttu-id="9bbd3-104">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="9bbd3-104">SecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bbd3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9bbd3-105">Syntax</span></span>  
  
```csharp
class SecurityBindingElement : BindingElement  
{  
  string DefaultAlgorithmSuite;  
  boolean IncludeTimestamp;  
  string KeyEntropyMode;  
  LocalServiceSecuritySettings LocalServiceSecuritySettings;  
  string MessageSecurityVersion;  
  string SecurityHeaderLayout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="9bbd3-106">메서드</span><span class="sxs-lookup"><span data-stu-id="9bbd3-106">Methods</span></span>  

 <span data-ttu-id="9bbd3-107">SecurityBindingElement 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bbd3-107">The SecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="9bbd3-108">속성</span><span class="sxs-lookup"><span data-stu-id="9bbd3-108">Properties</span></span>  

 <span data-ttu-id="9bbd3-109">SecurityBindingElement 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bbd3-109">The SecurityBindingElement class has the following properties:</span></span>  
  
### <a name="defaultalgorithmsuite"></a><span data-ttu-id="9bbd3-110">DefaultAlgorithmSuite</span><span class="sxs-lookup"><span data-stu-id="9bbd3-110">DefaultAlgorithmSuite</span></span>  

 <span data-ttu-id="9bbd3-111">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="9bbd3-111">Data type: string</span></span>  
  
 <span data-ttu-id="9bbd3-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9bbd3-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9bbd3-113">바인딩과 함께 사용할 알고리즘을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbd3-113">Specifies the algorithms to use with the binding.</span></span>  
  
### <a name="includetimestamp"></a><span data-ttu-id="9bbd3-114">IncludeTimestamp</span><span class="sxs-lookup"><span data-stu-id="9bbd3-114">IncludeTimestamp</span></span>  

 <span data-ttu-id="9bbd3-115">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="9bbd3-115">Data type: boolean</span></span>  
  
 <span data-ttu-id="9bbd3-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9bbd3-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9bbd3-117">각 메시지에 타임스탬프가 포함되는지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9bbd3-117">A Boolean value that specifies whether each message contains a timestamp.</span></span>  
  
### <a name="keyentropymode"></a><span data-ttu-id="9bbd3-118">KeyEntropyMode</span><span class="sxs-lookup"><span data-stu-id="9bbd3-118">KeyEntropyMode</span></span>  

 <span data-ttu-id="9bbd3-119">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="9bbd3-119">Data type: string</span></span>  
  
 <span data-ttu-id="9bbd3-120">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9bbd3-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9bbd3-121">키를 만드는 데 사용되는 엔트로피의 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="9bbd3-121">The source of entropy used to create keys.</span></span>  
  
### <a name="localservicesecuritysettings"></a><span data-ttu-id="9bbd3-122">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="9bbd3-122">LocalServiceSecuritySettings</span></span>  

 <span data-ttu-id="9bbd3-123">데이터 형식: LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="9bbd3-123">Data type: LocalServiceSecuritySettings</span></span>  
  
 <span data-ttu-id="9bbd3-124">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9bbd3-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9bbd3-125">로컬 서비스에 대한 바인딩 특정 보안 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="9bbd3-125">The binding specific security properties for the local service.</span></span>  
  
### <a name="messagesecurityversion"></a><span data-ttu-id="9bbd3-126">MessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="9bbd3-126">MessageSecurityVersion</span></span>  

 <span data-ttu-id="9bbd3-127">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="9bbd3-127">Data type: string</span></span>  
  
 <span data-ttu-id="9bbd3-128">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9bbd3-128">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9bbd3-129">메시지 보안에 사용된 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="9bbd3-129">The version used for message security.</span></span>  
  
### <a name="securityheaderlayout"></a><span data-ttu-id="9bbd3-130">SecurityHeaderLayout</span><span class="sxs-lookup"><span data-stu-id="9bbd3-130">SecurityHeaderLayout</span></span>  

 <span data-ttu-id="9bbd3-131">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="9bbd3-131">Data type: string</span></span>  
  
 <span data-ttu-id="9bbd3-132">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9bbd3-132">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9bbd3-133">이 바인딩의 보안 헤더에 있는 요소의 순서입니다.</span><span class="sxs-lookup"><span data-stu-id="9bbd3-133">The order of elements in the security header for this binding.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9bbd3-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9bbd3-134">Requirements</span></span>  
  
|<span data-ttu-id="9bbd3-135">MOF</span><span class="sxs-lookup"><span data-stu-id="9bbd3-135">MOF</span></span>|<span data-ttu-id="9bbd3-136">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bbd3-136">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="9bbd3-137">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="9bbd3-137">Namespace</span></span>|<span data-ttu-id="9bbd3-138">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bbd3-138">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9bbd3-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9bbd3-139">See also</span></span>

- <xref:System.ServiceModel.Channels.SecurityBindingElement>
