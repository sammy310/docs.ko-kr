---
title: '방법: 사용자 지정 클레임 만들기'
description: WCF에서 사용자 지정 클레임을 만드는 방법에 대해 알아봅니다. WCF는 다양 한 기본 제공 클레임을 지원 하 고 일부 응용 프로그램에는 사용자 지정 클레임이 필요할 수 있습니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d619976b-eda3-475e-ac23-c7988a2dceb0
ms.openlocfilehash: 89f2b1359b48b71720db6ff38f27883745cfe612
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247548"
---
# <a name="how-to-create-a-custom-claim"></a><span data-ttu-id="b5e07-104">방법: 사용자 지정 클레임 만들기</span><span class="sxs-lookup"><span data-stu-id="b5e07-104">How to: Create a Custom Claim</span></span>
<span data-ttu-id="b5e07-105">WCF (Windows Communication Foundation)의 Id 모델 인프라에서는 <xref:System.IdentityModel.Claims.Claim> 이러한 형식 및 권한으로 인스턴스를 만들기 위한 도우미 함수를 사용 하 여 기본 제공 클레임 형식 및 권한 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e07-105">The Identity Model infrastructure in Windows Communication Foundation (WCF) provides a set of built-in claim types and rights with the helper functions for creating <xref:System.IdentityModel.Claims.Claim> instances with those types and rights.</span></span> <span data-ttu-id="b5e07-106">이러한 기본 제공 클레임은 WCF에서 기본적으로 지 원하는 클라이언트 자격 증명 형식에 있는 정보를 모델링 하도록 디자인 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e07-106">These built-in claims are designed to model information found in client credential types that WCF supports by default.</span></span> <span data-ttu-id="b5e07-107">일반적으로 기본 제공 클레임으로 충분하지만 일부 애플리케이션에는 사용자 지정 클레임이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e07-107">In many cases, the built-in claims are sufficient; however some applications may require custom claims.</span></span> <span data-ttu-id="b5e07-108">클레임은 클레임 형식, 클레임이 적용되는 리소스 및 해당 리소스에 대해 어설션되는 권한으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5e07-108">A claim consists of the claim type, the resource for which the claim applies to and the right that is asserted over that resource.</span></span> <span data-ttu-id="b5e07-109">이 항목에서는 사용자 지정 클레임을 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e07-109">This topic describes how to create a custom claim.</span></span>  
  
### <a name="to-create-a-custom-claim-that-is-based-on-a-primitive-data-type"></a><span data-ttu-id="b5e07-110">기본 데이터 형식을 기반으로 사용자 지정 클레임을 만들려면</span><span class="sxs-lookup"><span data-stu-id="b5e07-110">To create a custom claim that is based on a primitive data type</span></span>  
  
1. <span data-ttu-id="b5e07-111">클레임 형식, 리소스 값 및 권한을 <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29> 생성자에 전달하여 사용자 지정 클레임을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b5e07-111">Create a custom claim by passing the claim type, resource value and right to the <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29> constructor.</span></span>  
  
    1. <span data-ttu-id="b5e07-112">클레임 형식의 고유 값을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e07-112">Decide on a unique value for the claim type.</span></span>  
  
         <span data-ttu-id="b5e07-113">클레임 형식은 고유한 문자열 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="b5e07-113">The claim type is a unique string identifier.</span></span> <span data-ttu-id="b5e07-114">클레임 형식에 사용되는 문자열 식별자를 고유하게 설정하는 작업은 사용자 지정 클레임 디자이너가 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e07-114">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the claim type is unique.</span></span> <span data-ttu-id="b5e07-115">WCF에 의해 정의 되는 클레임 형식 목록은 클래스를 참조 하세요 <xref:System.IdentityModel.Claims.ClaimTypes> .</span><span class="sxs-lookup"><span data-stu-id="b5e07-115">For a list of claim types that are defined by WCF, see the <xref:System.IdentityModel.Claims.ClaimTypes> class.</span></span>  
  
    2. <span data-ttu-id="b5e07-116">기본 데이터 형식과 리소스 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e07-116">Choose the primitive data type and value for the resource.</span></span>  
  
         <span data-ttu-id="b5e07-117">리소스는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="b5e07-117">A resource is an object.</span></span> <span data-ttu-id="b5e07-118">리소스의 CLR 형식은 기본(예: <xref:System.String> 또는 <xref:System.Int32>)이나 serialize할 수 있는 모든 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e07-118">The CLR type of the resource can be a primitive, such as <xref:System.String> or <xref:System.Int32>, or any serializable type.</span></span> <span data-ttu-id="b5e07-119">WCF에 의해 다양 한 지점에서 클레임이 serialize 되기 때문에 리소스의 CLR 형식을 serialize 할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e07-119">The CLR type of the resource must be serializable, because claims are serialized at various points by WCF.</span></span> <span data-ttu-id="b5e07-120">기본 형식은 serialize할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e07-120">Primitive types are serializable.</span></span>  
  
    3. <span data-ttu-id="b5e07-121">WCF에서 정의한 권한을 선택 하거나 사용자 지정 권한에 대해 고유한 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e07-121">Choose a right that is defined by WCF or a unique value for a custom right.</span></span>  
  
         <span data-ttu-id="b5e07-122">권한은 고유한 문자열 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="b5e07-122">A right is a unique string identifier.</span></span> <span data-ttu-id="b5e07-123">WCF에 의해 정의 되는 권한은 클래스에서 정의 됩니다 <xref:System.IdentityModel.Claims.Rights> .</span><span class="sxs-lookup"><span data-stu-id="b5e07-123">The rights that are defined by WCF are defined in the <xref:System.IdentityModel.Claims.Rights> class.</span></span>  
  
         <span data-ttu-id="b5e07-124">권한에 사용되는 문자열 식별자를 고유하게 설정하는 작업은 사용자 지정 클레임 디자이너가 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e07-124">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the right is unique.</span></span>  
  
         <span data-ttu-id="b5e07-125">다음 코드 예제에서는 `http://example.org/claims/simplecustomclaim` 권한을 사용하여 `Driver's License`라는 리소스에 대해 클레임 형식이 <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>인 사용자 지정 클레임을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b5e07-125">The following code example creates a custom claim with a claim type of `http://example.org/claims/simplecustomclaim`, for a resource named `Driver's License`, and with the <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> right.</span></span>  
  
     [!code-csharp[c_CustomClaim#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#4)]
     [!code-vb[c_CustomClaim#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#4)]  
  
### <a name="to-create-a-custom-claim-that-is-based-on-a-non-primitive-data-type"></a><span data-ttu-id="b5e07-126">기본이 아닌 데이터 형식을 기반으로 사용자 지정 클레임을 만들려면</span><span class="sxs-lookup"><span data-stu-id="b5e07-126">To create a custom claim that is based on a non-primitive data type</span></span>  
  
1. <span data-ttu-id="b5e07-127">클레임 형식, 리소스 값 및 권한을 <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29> 생성자에 전달하여 사용자 지정 클레임을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b5e07-127">Create a custom claim by passing the claim type, resource value and right to the <xref:System.IdentityModel.Claims.Claim.%23ctor%28System.String%2CSystem.Object%2CSystem.String%29> constructor.</span></span>  
  
    1. <span data-ttu-id="b5e07-128">클레임 형식의 고유 값을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e07-128">Decide on a unique value for the claim type.</span></span>  
  
         <span data-ttu-id="b5e07-129">클레임 형식은 고유한 문자열 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="b5e07-129">The claim type is a unique string identifier.</span></span> <span data-ttu-id="b5e07-130">클레임 형식에 사용되는 문자열 식별자를 고유하게 설정하는 작업은 사용자 지정 클레임 디자이너가 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e07-130">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the claim type is unique.</span></span> <span data-ttu-id="b5e07-131">WCF에 의해 정의 되는 클레임 형식 목록은 클래스를 참조 하세요 <xref:System.IdentityModel.Claims.ClaimTypes> .</span><span class="sxs-lookup"><span data-stu-id="b5e07-131">For a list of claim types that are defined by WCF, see the <xref:System.IdentityModel.Claims.ClaimTypes> class.</span></span>  
  
    2. <span data-ttu-id="b5e07-132">serialize할 수 있는 기본이 아닌 리소스 형식을 선택하거나 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e07-132">Choose or define a serializable non-primitive type for the resource.</span></span>  
  
         <span data-ttu-id="b5e07-133">리소스는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="b5e07-133">A resource is an object.</span></span> <span data-ttu-id="b5e07-134">WCF에 의해 다양 한 지점에서 클레임이 serialize 되기 때문에 리소스의 CLR 형식을 serialize 할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e07-134">The CLR type of the resource must be serializable, because claims are serialized at various points by WCF.</span></span> <span data-ttu-id="b5e07-135">기본 형식은 이미 serialize할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e07-135">Primitive types are already serializable.</span></span>  
  
         <span data-ttu-id="b5e07-136">새 형식을 정의하는 경우 <xref:System.Runtime.Serialization.DataContractAttribute>를 클래스에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e07-136">When a new type is defined, apply the <xref:System.Runtime.Serialization.DataContractAttribute> to the class.</span></span> <span data-ttu-id="b5e07-137">또한 클레임의 일부로 serialize할 수 있어야 하는 새 형식의 모든 멤버에 <xref:System.Runtime.Serialization.DataMemberAttribute> 특성을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e07-137">Also apply the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to the all members of the new type that need to be serialized as part of the claim.</span></span>  
  
         <span data-ttu-id="b5e07-138">다음 코드 예제에서는 `MyResourceType`이라는 사용자 지정 리소스 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e07-138">The following code example defines a custom resource type named `MyResourceType`.</span></span>  
  
         [!code-csharp[c_CustomClaim#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#2)]
         [!code-vb[c_CustomClaim#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#2)]
  
    3. <span data-ttu-id="b5e07-139">WCF에서 정의한 권한을 선택 하거나 사용자 지정 권한에 대해 고유한 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e07-139">Choose a right that is defined by WCF or a unique value for a custom right.</span></span>  
  
         <span data-ttu-id="b5e07-140">권한은 고유한 문자열 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="b5e07-140">A right is a unique string identifier.</span></span> <span data-ttu-id="b5e07-141">WCF에 의해 정의 되는 권한은 클래스에서 정의 됩니다 <xref:System.IdentityModel.Claims.Rights> .</span><span class="sxs-lookup"><span data-stu-id="b5e07-141">The rights that are defined by WCF are defined in the <xref:System.IdentityModel.Claims.Rights> class.</span></span>  
  
         <span data-ttu-id="b5e07-142">권한에 사용되는 문자열 식별자를 고유하게 설정하는 작업은 사용자 지정 클레임 디자이너가 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e07-142">It is the custom claim designer's responsibility to ensure that the string identifier that is used for the right is unique.</span></span>  
  
         <span data-ttu-id="b5e07-143">다음 코드 예제에서는 `http://example.org/claims/complexcustomclaim` 권한을 사용하여 클레임 형식이 `MyResourceType`이고 사용자 지정 리소스 형식이 <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>인 사용자 지정 클레임을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b5e07-143">The following code example creates a custom claim with a claim type of `http://example.org/claims/complexcustomclaim`, a custom resource type of `MyResourceType`, and with the <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> right.</span></span>  
  
         [!code-csharp[c_CustomClaim#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#5)]
         [!code-vb[c_CustomClaim#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#5)]
  
## <a name="example"></a><span data-ttu-id="b5e07-144">예제</span><span class="sxs-lookup"><span data-stu-id="b5e07-144">Example</span></span>  
 <span data-ttu-id="b5e07-145">다음 코드 예제에서는 기본 리소스 형식의 사용자 지정 클레임과 기본이 아닌 리소스 형식의 사용자 지정 클레임을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b5e07-145">The following code example demonstrates how to create a custom claim with a primitive resource type and a custom claim with a non-primitive resource type.</span></span>  
  
 [!code-csharp[c_CustomClaim#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaim/cs/c_customclaim.cs#0)]
 [!code-vb[c_CustomClaim#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaim/vb/c_customclaim.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="b5e07-146">참조</span><span class="sxs-lookup"><span data-stu-id="b5e07-146">See also</span></span>

- <xref:System.IdentityModel.Claims.Claim>
- <xref:System.IdentityModel.Claims.Rights>
- <xref:System.IdentityModel.Claims.ClaimTypes>
- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- [<span data-ttu-id="b5e07-147">ID 모델을 사용하여 클레임 및 권한 부여 관리</span><span class="sxs-lookup"><span data-stu-id="b5e07-147">Managing Claims and Authorization with the Identity Model</span></span>](../feature-details/managing-claims-and-authorization-with-the-identity-model.md)
