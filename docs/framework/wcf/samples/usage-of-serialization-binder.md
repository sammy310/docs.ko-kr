---
title: Serialization 바인더 사용
ms.date: 03/30/2017
ms.assetid: ab46c087-200c-45bf-9c95-5a6cda6e8b98
ms.openlocfilehash: bfce2a14c8757250c520919c8ff2a4d7048a9d5c
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2019
ms.locfileid: "74138651"
---
# <a name="usage-of-serialization-binder"></a><span data-ttu-id="12654-102">Serialization 바인더 사용</span><span class="sxs-lookup"><span data-stu-id="12654-102">Usage of Serialization Binder</span></span>
<span data-ttu-id="12654-103">이 샘플에서는 <xref:System.Runtime.Serialization.SerializationBinder>를 사용하여 제네릭 형식이 serialize될 때 이 형식의 버전을 변경하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="12654-103">This sample shows how to use the <xref:System.Runtime.Serialization.SerializationBinder> to change the version of a generic type when it is serialized.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="12654-104">세부 항목</span><span class="sxs-lookup"><span data-stu-id="12654-104">Demonstrates</span></span>  
 <span data-ttu-id="12654-105"><xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter></span><span class="sxs-lookup"><span data-stu-id="12654-105"><xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter></span></span>  
  
## <a name="discussion"></a><span data-ttu-id="12654-106">토론</span><span class="sxs-lookup"><span data-stu-id="12654-106">Discussion</span></span>  
 <span data-ttu-id="12654-107">이 샘플에서는 서로 다른 버전의 .NET Framework를 대상으로 하는 두 엔터티가 이진 포맷터 및 serialization 바인더를 사용 하 여 통신할 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="12654-107">This sample shows how two entities that are targeting different versions of the .NET Framework can communicate using the binary formatter and the serialization binder.</span></span>  
  
<span data-ttu-id="12654-108">이 샘플은 .NET Remoting을 사용 하 여 개발 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="12654-108">This sample was developed using .NET Remoting.</span></span> <span data-ttu-id="12654-109">이는 .NET Framework 4를 대상으로 하는 서버로 구성 됩니다 .이 서버는 제네릭 형식을 사용 하는 계약을 구현 하 고 두 개의 다른 클라이언트 .NET Framework 2.0를 대상으로 하며 다른 하나는 .NET Framework 4입니다.</span><span class="sxs-lookup"><span data-stu-id="12654-109">It consists of a server targeting .NET Framework 4, which implements a contract with generic types, and two different clients, one targeting .NET Framework 2.0 and another targeting .NET Framework 4.</span></span>  
  
 <span data-ttu-id="12654-110">서버에서는 <xref:System.Runtime.Serialization.SerializationBinder>를 이진 포맷터에 연결하여 serialization 시 형식 버전을 적절하게 변경할 수 있도록 하므로 두 클라이언트 모두 해당 형식을 올바르게 역직렬화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12654-110">The server attaches a <xref:System.Runtime.Serialization.SerializationBinder> to the binary formatter to be able to change the version of the types accordingly on serialization, so both clients can deserialize those types properly.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="12654-111">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="12654-111">To set up, build and run the sample</span></span>  
  
1. <span data-ttu-id="12654-112">클라이언트를 실행 하려면 솔루션을 마우스 오른쪽 단추로 클릭 하 고 (프로젝트 6 개) SBGenericsVTS **속성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="12654-112">To execute the client, right-click the solution, SBGenericsVTS (6 projects) and then select **Properties**.</span></span>  
  
2. <span data-ttu-id="12654-113">**공용 속성**에서 **시작 프로젝트**를 선택한 다음 **여러 개의 시작 프로젝트**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="12654-113">In **Common Properties**, select **Startup Project**, then select **Multiple Startup Projects**.</span></span>  
  
3. <span data-ttu-id="12654-114">**서버** 를 먼저 선택 하 고 **Client20** 한 다음 **Client40**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="12654-114">Select **Server** first, then **Client20** and then **Client40**.</span></span> <span data-ttu-id="12654-115">이러한 3 개의 프로젝트에 대 한 **시작** 작업을 선택 하 고 나머지는 **없음**으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="12654-115">Select the **Start** action to these three projects and leave the rest set to **None**.</span></span>  
  
4. <span data-ttu-id="12654-116">**확인** 을 클릭 한 다음 f5 키를 눌러 샘플을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="12654-116">Click **OK** and then press F5 to run the sample.</span></span>
