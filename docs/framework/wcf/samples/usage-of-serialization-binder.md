---
title: Serialization 바인더 사용
ms.date: 03/30/2017
ms.assetid: ab46c087-200c-45bf-9c95-5a6cda6e8b98
ms.openlocfilehash: 10900950b935b484053fe8e37263f0dfc25eba99
ms.sourcegitcommit: 127343afce8422bfa944c8b0c4ecc8f79f653255
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2019
ms.locfileid: "67348453"
---
# <a name="usage-of-serialization-binder"></a><span data-ttu-id="b49a1-102">Serialization 바인더 사용</span><span class="sxs-lookup"><span data-stu-id="b49a1-102">Usage of Serialization Binder</span></span>
<span data-ttu-id="b49a1-103">이 샘플에서는 <xref:System.Runtime.Serialization.SerializationBinder>를 사용하여 제네릭 형식이 serialize될 때 이 형식의 버전을 변경하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b49a1-103">This sample shows how to use the <xref:System.Runtime.Serialization.SerializationBinder> to change the version of a generic type when it is serialized.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="b49a1-104">세부 항목</span><span class="sxs-lookup"><span data-stu-id="b49a1-104">Demonstrates</span></span>  
 <span data-ttu-id="b49a1-105"><xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter></span><span class="sxs-lookup"><span data-stu-id="b49a1-105"><xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter></span></span>  
  
## <a name="discussion"></a><span data-ttu-id="b49a1-106">토론</span><span class="sxs-lookup"><span data-stu-id="b49a1-106">Discussion</span></span>  
 <span data-ttu-id="b49a1-107">이 샘플은.NET Framework 수의 서로 다른 버전을 대상 통신할 수 있는지 이진 포맷터와 serialization 바인더를 사용 하 여 두 엔터티를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b49a1-107">This sample shows how two entities that are targeting different versions of the .NET Framework can communicate using the binary formatter and the serialization binder.</span></span>  
  
<span data-ttu-id="b49a1-108">이 샘플은.NET Remoting을 사용 하 여 개발 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b49a1-108">This sample was developed using .NET Remoting.</span></span> <span data-ttu-id="b49a1-109">대상으로 하는 서버 이루어져 [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)], 제네릭 형식 및 두 명의 다른 클라이언트, 하나의 대상.NET Framework 2.0 및 다른 대상으로 하는 계약을 구현 하는 [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="b49a1-109">It consists of a server targeting [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)], which implements a contract with generic types, and two different clients, one targeting .NET Framework 2.0 and another targeting [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)].</span></span>  
  
 <span data-ttu-id="b49a1-110">서버에서는 <xref:System.Runtime.Serialization.SerializationBinder>를 이진 포맷터에 연결하여 serialization 시 형식 버전을 적절하게 변경할 수 있도록 하므로 두 클라이언트 모두 해당 형식을 올바르게 deserialize할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b49a1-110">The server attaches a <xref:System.Runtime.Serialization.SerializationBinder> to the binary formatter to be able to change the version of the types accordingly on serialization, so both clients can deserialize those types properly.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b49a1-111">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="b49a1-111">To set up, build and run the sample</span></span>  
  
1. <span data-ttu-id="b49a1-112">클라이언트를 실행 하려면 SBGenericsVTS 솔루션을 마우스 오른쪽 단추로 클릭 (6 개 프로젝트)를 선택한 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="b49a1-112">To execute the client, right-click the solution, SBGenericsVTS (6 projects) and then select **Properties**.</span></span>  
  
2. <span data-ttu-id="b49a1-113">**공용 속성**를 선택 **시작 프로젝트**을 선택한 후 **여러 개의 시작 프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="b49a1-113">In **Common Properties**, select **Startup Project**, then select **Multiple Startup Projects**.</span></span>  
  
3. <span data-ttu-id="b49a1-114">선택 **Server** 먼저 **Client20** 차례로 **Client40**합니다.</span><span class="sxs-lookup"><span data-stu-id="b49a1-114">Select **Server** first, then **Client20** and then **Client40**.</span></span> <span data-ttu-id="b49a1-115">선택 된 **시작** 이 세 가지 프로젝트 작업과 나머지 **None**합니다.</span><span class="sxs-lookup"><span data-stu-id="b49a1-115">Select the **Start** action to these three projects and leave the rest set to **None**.</span></span>  
  
4. <span data-ttu-id="b49a1-116">클릭 **확인** 한 다음 f5 키를 눌러 샘플을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b49a1-116">Click **OK** and then press F5 to run the sample.</span></span>
