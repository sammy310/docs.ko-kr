---
description: '자세한 정보: Serialization 바인더 사용'
title: Serialization 바인더 사용
ms.date: 03/30/2017
ms.assetid: ab46c087-200c-45bf-9c95-5a6cda6e8b98
ms.openlocfilehash: ee00d8049ae644525f8013801dc7c453b9ad5aeb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99798175"
---
# <a name="usage-of-serialization-binder"></a><span data-ttu-id="bcc78-103">Serialization 바인더 사용</span><span class="sxs-lookup"><span data-stu-id="bcc78-103">Usage of Serialization Binder</span></span>

<span data-ttu-id="bcc78-104">이 샘플에서는 <xref:System.Runtime.Serialization.SerializationBinder>를 사용하여 제네릭 형식이 serialize될 때 이 형식의 버전을 변경하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bcc78-104">This sample shows how to use the <xref:System.Runtime.Serialization.SerializationBinder> to change the version of a generic type when it is serialized.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="bcc78-105">데모</span><span class="sxs-lookup"><span data-stu-id="bcc78-105">Demonstrates</span></span>  

 <span data-ttu-id="bcc78-106"><xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter></span><span class="sxs-lookup"><span data-stu-id="bcc78-106"><xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter></span></span>  
  
## <a name="discussion"></a><span data-ttu-id="bcc78-107">토론(Discussion)</span><span class="sxs-lookup"><span data-stu-id="bcc78-107">Discussion</span></span>  

 <span data-ttu-id="bcc78-108">이 샘플에서는 서로 다른 버전의 .NET Framework를 대상으로 하는 두 엔터티가 이진 포맷터 및 serialization 바인더를 사용 하 여 통신할 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bcc78-108">This sample shows how two entities that are targeting different versions of the .NET Framework can communicate using the binary formatter and the serialization binder.</span></span>  
  
<span data-ttu-id="bcc78-109">이 샘플은 .NET Remoting을 사용 하 여 개발 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bcc78-109">This sample was developed using .NET Remoting.</span></span> <span data-ttu-id="bcc78-110">이는 .NET Framework 4를 대상으로 하는 서버로 구성 됩니다 .이 서버는 제네릭 형식을 사용 하는 계약을 구현 하 고 두 개의 다른 클라이언트 .NET Framework 2.0를 대상으로 하며 다른 하나는 .NET Framework 4입니다.</span><span class="sxs-lookup"><span data-stu-id="bcc78-110">It consists of a server targeting .NET Framework 4, which implements a contract with generic types, and two different clients, one targeting .NET Framework 2.0 and another targeting .NET Framework 4.</span></span>  
  
 <span data-ttu-id="bcc78-111">서버에서는 <xref:System.Runtime.Serialization.SerializationBinder>를 이진 포맷터에 연결하여 serialization 시 형식 버전을 적절하게 변경할 수 있도록 하므로 두 클라이언트 모두 해당 형식을 올바르게 역직렬화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcc78-111">The server attaches a <xref:System.Runtime.Serialization.SerializationBinder> to the binary formatter to be able to change the version of the types accordingly on serialization, so both clients can deserialize those types properly.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="bcc78-112">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="bcc78-112">To set up, build and run the sample</span></span>  
  
1. <span data-ttu-id="bcc78-113">클라이언트를 실행 하려면 솔루션을 마우스 오른쪽 단추로 클릭 하 고 (프로젝트 6 개) SBGenericsVTS **속성** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcc78-113">To execute the client, right-click the solution, SBGenericsVTS (6 projects) and then select **Properties**.</span></span>  
  
2. <span data-ttu-id="bcc78-114">**공용 속성** 에서 **시작 프로젝트** 를 선택한 다음 **여러 개의 시작 프로젝트** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcc78-114">In **Common Properties**, select **Startup Project**, then select **Multiple Startup Projects**.</span></span>  
  
3. <span data-ttu-id="bcc78-115">**서버** 를 먼저 선택 하 고 **Client20** 한 다음 **Client40** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcc78-115">Select **Server** first, then **Client20** and then **Client40**.</span></span> <span data-ttu-id="bcc78-116">이러한 3 개의 프로젝트에 대 한 **시작** 작업을 선택 하 고 나머지는 **없음** 으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcc78-116">Select the **Start** action to these three projects and leave the rest set to **None**.</span></span>  
  
4. <span data-ttu-id="bcc78-117">**확인** 을 클릭 한 다음 f5 키를 눌러 샘플을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcc78-117">Click **OK** and then press F5 to run the sample.</span></span>
