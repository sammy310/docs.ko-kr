---
title: WS-MetadataExchange 바인딩
ms.date: 03/30/2017
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
ms.openlocfilehash: 03e6e6d5ee7e69b397acd0f51b8037f02c1804ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61795477"
---
# <a name="ws-metadataexchange-bindings"></a><span data-ttu-id="6fef4-102">WS-MetadataExchange 바인딩</span><span class="sxs-lookup"><span data-stu-id="6fef4-102">WS-MetadataExchange Bindings</span></span>
<span data-ttu-id="6fef4-103">이 항목에서는 여러 가지 전송에 대해 기본 메타데이터 교환 바인딩을 생성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6fef4-103">This topic describes how the default metadata exchange bindings are constructed for various transports.</span></span>  
  
## <a name="the-default-bindings"></a><span data-ttu-id="6fef4-104">기본 바인딩</span><span class="sxs-lookup"><span data-stu-id="6fef4-104">The Default Bindings</span></span>  
  
|<span data-ttu-id="6fef4-105">기본 바인딩 이름</span><span class="sxs-lookup"><span data-stu-id="6fef4-105">Default Binding Name</span></span>|<span data-ttu-id="6fef4-106">바인딩 생성 방법</span><span class="sxs-lookup"><span data-stu-id="6fef4-106">How the binding is constructed</span></span>|  
|--------------------------|------------------------------------|  
|<span data-ttu-id="6fef4-107">mexHttpBinding</span><span class="sxs-lookup"><span data-stu-id="6fef4-107">mexHttpBinding</span></span>|<span data-ttu-id="6fef4-108">전송 수준 보안이 비활성화된 <xref:System.ServiceModel.WSHttpBinding>입니다.</span><span class="sxs-lookup"><span data-stu-id="6fef4-108">A <xref:System.ServiceModel.WSHttpBinding> with transport-level security disabled.</span></span>|  
|<span data-ttu-id="6fef4-109">mexHttpsBinding</span><span class="sxs-lookup"><span data-stu-id="6fef4-109">mexHttpsBinding</span></span>|<span data-ttu-id="6fef4-110">전송 수준 보안을 지원하는 <xref:System.ServiceModel.WSHttpBinding>입니다.</span><span class="sxs-lookup"><span data-stu-id="6fef4-110">A <xref:System.ServiceModel.WSHttpBinding> that supports transport-level security.</span></span>|  
|<span data-ttu-id="6fef4-111">mexNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="6fef4-111">mexNamedPipeBinding</span></span>|<span data-ttu-id="6fef4-112">기본값을 사용하는 <xref:System.ServiceModel.Channels.CustomBinding>가 있는 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>입니다.</span><span class="sxs-lookup"><span data-stu-id="6fef4-112">A  <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> using the default values.</span></span>|  
|<span data-ttu-id="6fef4-113">mexTcpBinding</span><span class="sxs-lookup"><span data-stu-id="6fef4-113">mexTcpBinding</span></span>|<span data-ttu-id="6fef4-114">기본값을 사용하는 <xref:System.ServiceModel.Channels.CustomBinding>가 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>입니다.</span><span class="sxs-lookup"><span data-stu-id="6fef4-114">A <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.TcpTransportBindingElement> using default values.</span></span>|
