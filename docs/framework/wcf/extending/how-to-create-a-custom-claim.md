---
title: '방법: 사용자 지정 클레임 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d619976b-eda3-475e-ac23-c7988a2dceb0
ms.openlocfilehash: 399aba1a6ad70ae37355f529a291ab2f604af03f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70797080"
---
# <a name="how-to-create-a-custom-claim"></a><span data-ttu-id="26938-102">방법: 사용자 지정 클레임 만들기</span><span class="sxs-lookup"><span data-stu-id="26938-102">How to: Create a Custom Claim</span></span>
<span data-ttu-id="26938-103">WCF (Windows Communication Foundation)의 id 모델 인프라에서는 이러한 형식 및 권한으로 인스턴스를 만들기 <xref:System.IdentityModel.Claims.Claim> 위한 도우미 함수를 사용 하 여 기본 제공 클레임 형식 및 권한 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="26938-103">The Identity Model infrastructure in Windows Communication Foundation (WCF) provides a set of built-in claim types and rights with the helper functions for creating <xref:System.IdentityModel.Claims.Claim> instances with those types and rights.</span></span> <span data-ttu-id="26938-104">이러한 기본 제공 클레임은 WCF에서 기본적으로 지 원하는 클라이언트 자격 증명 형식에 있는 정보를 모델링 하도록 디자인 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="26938-104">These built-in claims are designed to model information found in client credential types that WCF supports by default.</span></span> <span data-ttu-id="26938-105">일반적으로 기본 제공 클레임으로 충분하지만 일부 애플리케이션에는 사용자 지정 클레임이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26938-105">In many cases, the built-in claims are sufficient; however some applications may require custom claims.</span></span> <span data-ttu-id="26938-106">클레임은 클레임 형식, 클레임이 적용되는 리소스 및 해당 리소스에 대해 어설션되는 권한으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="26938-106">A claim consists of the claim type, the resource for which the claim applies to and the right that is asserted over that resource.</span></span> <span data-ttu-id="26938-107">이 항목에서는 사용자 지정 클레임을 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="26938-107">This topic describes how to create a custom claim.</span></span>  
  
### <a name="to-create-a-custom-claim-that-is-based-on-a-primitive-data-type"></a><span data-ttu-id="26938-108">기본 데이터 형식을 기반으로 사용자 지정 클레임을 만들려면</span><span class="sxs-lookup"><span data-stu-id="26938-108">To create a custom claim that is based on a primitive data type</span></span>  
  
1. <span data-ttu-id="26938-109">클레임 형식, 리소스 값 및 권한을 <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29> 생성자에 전달하여 사용자 지정 클레임을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="26938-109">Create a custom claim by passing the claim type, resource value and right to the <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29> constructor.</span></span>  
  
    1. <span data-ttu-id="26938-110">클레임 형식의 고유 값을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="26938-110">Decide on a unique value for the claim type.</span></span>  
  
         <span data-ttu-id="26938-111">클레임 형식은 고유한 문자열 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="26938-111">The claim type is a unique string identifier.</span></span> <span data-ttu-id="26938-112">클레임 형식에 사용되는 문자열 식별자를 고유하게 설정하는 작업은 사용자 지정 클레임 디자이너가 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="26938-112">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the claim type is unique.</span></span> <span data-ttu-id="26938-113">WCF에 의해 정의 되는 클레임 형식 목록은 <xref:System.IdentityModel.Claims.ClaimTypes> 클래스를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="26938-113">For a list of claim types that are defined by WCF, see the <xref:System.IdentityModel.Claims.ClaimTypes> class.</span></span>  
  
    2. <span data-ttu-id="26938-114">기본 데이터 형식과 리소스 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="26938-114">Choose the primitive data type and value for the resource.</span></span>  
  
         <span data-ttu-id="26938-115">리소스는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="26938-115">A resource is an object.</span></span> <span data-ttu-id="26938-116">리소스의 CLR 형식은 기본(예: <xref:System.String> 또는 <xref:System.Int32>)이나 serialize할 수 있는 모든 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26938-116">The CLR type of the resource can be a primitive, such as <xref:System.String> or <xref:System.Int32>, or any serializable type.</span></span> <span data-ttu-id="26938-117">WCF에 의해 다양 한 지점에서 클레임이 serialize 되기 때문에 리소스의 CLR 형식을 serialize 할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26938-117">The CLR type of the resource must be serializable, because claims are serialized at various points by WCF.</span></span> <span data-ttu-id="26938-118">기본 형식은 serialize할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26938-118">Primitive types are serializable.</span></span>  
  
    3. <span data-ttu-id="26938-119">WCF에서 정의한 권한을 선택 하거나 사용자 지정 권한에 대해 고유한 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="26938-119">Choose a right that is defined by WCF or a unique value for a custom right.</span></span>  
  
         <span data-ttu-id="26938-120">권한은 고유한 문자열 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="26938-120">A right is a unique string identifier.</span></span> <span data-ttu-id="26938-121">WCF에 의해 정의 되는 권한은 <xref:System.IdentityModel.Claims.Rights> 클래스에서 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26938-121">The rights that are defined by WCF are defined in the <xref:System.IdentityModel.Claims.Rights> class.</span></span>  
  
         <span data-ttu-id="26938-122">권한에 사용되는 문자열 식별자를 고유하게 설정하는 작업은 사용자 지정 클레임 디자이너가 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="26938-122">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the right is unique.</span></span>  
  
         <span data-ttu-id="26938-123">다음 코드 예제에서는 `http://example.org/claims/simplecustomclaim` 권한을 사용하여 `Driver's License`라는 리소스에 대해 클레임 형식이 <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>인 사용자 지정 클레임을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="26938-123">The following code example creates a custom claim with a claim type of `http://example.org/claims/simplecustomclaim`, for a resource named `Driver's License`, and with the <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> right.</span></span>  
  
     [!code-csharp[c_CustomClaim#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#4)]
     [!code-vb[c_CustomClaim#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#4)]  
  
### <a name="to-create-a-custom-claim-that-is-based-on-a-non-primitive-data-type"></a><span data-ttu-id="26938-124">기본이 아닌 데이터 형식을 기반으로 사용자 지정 클레임을 만들려면</span><span class="sxs-lookup"><span data-stu-id="26938-124">To create a custom claim that is based on a non-primitive data type</span></span>  
  
1. <span data-ttu-id="26938-125">클레임 형식, 리소스 값 및 권한을 <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29> 생성자에 전달하여 사용자 지정 클레임을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="26938-125">Create a custom claim by passing the claim type, resource value and right to the <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29> constructor.</span></span>  
  
    1. <span data-ttu-id="26938-126">클레임 형식의 고유 값을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="26938-126">Decide on a unique value for the claim type.</span></span>  
  
         <span data-ttu-id="26938-127">클레임 형식은 고유한 문자열 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="26938-127">The claim type is a unique string identifier.</span></span> <span data-ttu-id="26938-128">클레임 형식에 사용되는 문자열 식별자를 고유하게 설정하는 작업은 사용자 지정 클레임 디자이너가 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="26938-128">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the claim type is unique.</span></span> <span data-ttu-id="26938-129">WCF에 의해 정의 되는 클레임 형식 목록은 <xref:System.IdentityModel.Claims.ClaimTypes> 클래스를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="26938-129">For a list of claim types that are defined by WCF, see the <xref:System.IdentityModel.Claims.ClaimTypes> class.</span></span>  
  
    2. <span data-ttu-id="26938-130">serialize할 수 있는 기본이 아닌 리소스 형식을 선택하거나 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="26938-130">Choose or define a serializable non-primitive type for the resource.</span></span>  
  
         <span data-ttu-id="26938-131">리소스는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="26938-131">A resource is an object.</span></span> <span data-ttu-id="26938-132">WCF에 의해 다양 한 지점에서 클레임이 serialize 되기 때문에 리소스의 CLR 형식을 serialize 할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26938-132">The CLR type of the resource must be serializable, because claims are serialized at various points by WCF.</span></span> <span data-ttu-id="26938-133">기본 형식은 이미 serialize할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26938-133">Primitive types are already serializable.</span></span>  
  
         <span data-ttu-id="26938-134">새 형식을 정의하는 경우 <xref:System.Runtime.Serialization.DataContractAttribute>를 클래스에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="26938-134">When a new type is defined, apply the <xref:System.Runtime.Serialization.DataContractAttribute> to the class.</span></span> <span data-ttu-id="26938-135">또한 클레임의 일부로 serialize할 수 있어야 하는 새 형식의 모든 멤버에 <xref:System.Runtime.Serialization.DataMemberAttribute> 특성을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="26938-135">Also apply the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to the all members of the new type that need to be serialized as part of the claim.</span></span>  
  
         <span data-ttu-id="26938-136">다음 코드 예제에서는 `MyResourceType`이라는 사용자 지정 리소스 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="26938-136">The following code example defines a custom resource type named `MyResourceType`.</span></span>  
  
         [!code-csharp[c_CustomClaim#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#2)] 
         [!code-vb[c_CustomClaim#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#2)]        
  
    3. <span data-ttu-id="26938-137">WCF에서 정의한 권한을 선택 하거나 사용자 지정 권한에 대해 고유한 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="26938-137">Choose a right that is defined by WCF or a unique value for a custom right.</span></span>  
  
         <span data-ttu-id="26938-138">권한은 고유한 문자열 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="26938-138">A right is a unique string identifier.</span></span> <span data-ttu-id="26938-139">WCF에 의해 정의 되는 권한은 <xref:System.IdentityModel.Claims.Rights> 클래스에서 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26938-139">The rights that are defined by WCF are defined in the <xref:System.IdentityModel.Claims.Rights> class.</span></span>  
  
         <span data-ttu-id="26938-140">권한에 사용되는 문자열 식별자를 고유하게 설정하는 작업은 사용자 지정 클레임 디자이너가 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="26938-140">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the right is unique.</span></span>  
  
         <span data-ttu-id="26938-141">다음 코드 예제에서는 `http://example.org/claims/complexcustomclaim` 권한을 사용하여 클레임 형식이 `MyResourceType`이고 사용자 지정 리소스 형식이 <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>인 사용자 지정 클레임을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="26938-141">The following code example creates a custom claim with a claim type of `http://example.org/claims/complexcustomclaim`, a custom resource type of `MyResourceType`, and with the <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> right.</span></span>  
  
         [!code-csharp[c_CustomClaim#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#5)] 
         [!code-vb[c_CustomClaim#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#5)]     
  
## <a name="example"></a><span data-ttu-id="26938-142">예제</span><span class="sxs-lookup"><span data-stu-id="26938-142">Example</span></span>  
 <span data-ttu-id="26938-143">다음 코드 예제에서는 기본 리소스 형식의 사용자 지정 클레임과 기본이 아닌 리소스 형식의 사용자 지정 클레임을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="26938-143">The following code example demonstrates how to create a custom claim with a primitive resource type and a custom claim with a non-primitive resource type.</span></span>  
  
 [!code-csharp[c_CustomClaim#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#0)]
 [!code-vb[c_CustomClaim#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="26938-144">참고자료</span><span class="sxs-lookup"><span data-stu-id="26938-144">See also</span></span>

- <xref:System.IdentityModel.Claims.Claim>
- <xref:System.IdentityModel.Claims.Rights>
- <xref:System.IdentityModel.Claims.ClaimTypes>
- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- [<span data-ttu-id="26938-145">ID 모델을 사용하여 클레임 및 권한 부여 관리</span><span class="sxs-lookup"><span data-stu-id="26938-145">Managing Claims and Authorization with the Identity Model</span></span>](../feature-details/managing-claims-and-authorization-with-the-identity-model.md)
