---
title: 기존 노드 복사
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 2aa8f65c-cc62-4638-9c46-129dc15be786
ms.openlocfilehash: fb9ccd7b16d00355ba87bb32f5447906feeecd94
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711066"
---
# <a name="copy-existing-nodes"></a><span data-ttu-id="753fa-102">기존 노드 복사</span><span class="sxs-lookup"><span data-stu-id="753fa-102">Copy Existing Nodes</span></span>
<span data-ttu-id="753fa-103">XML DOM(문서 개체 모델)에는**SelectSingleNode**, **ChildNodes[int i]** , **Attributes[int i]** 등 노드를 선택하는 데 사용할 수 있는 여러 메서드와 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="753fa-103">There are many methods and properties in the XML Document Object Model (DOM)you can use to select a node, such as **SelectSingleNode**, **ChildNodes[int i]**, **Attributes[int i]**.</span></span> <span data-ttu-id="753fa-104">노드를 선택하면 특정 노드 형식에 작동하는 삽입 메서드 중 하나를 사용하여 트리에 해당 노드를 삽입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="753fa-104">Once the node is selected, you can insert it into the tree using one of the insert methods that work for that particular node type.</span></span> <span data-ttu-id="753fa-105">트리에 노드를 삽입하는 경우 유일한 제한 사항은 노드가 삽입된 후에도 문서가 제대로 구성되어야 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="753fa-105">The only restriction to inserting a node into the tree is that the document must still be well-formed after the node is inserted.</span></span> <span data-ttu-id="753fa-106">기존 노드를 DOM 트리에 삽입할 경우 해당 노드가 원래 위치에서 제거된 후에 대상 위치에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="753fa-106">When an existing node is inserted into the DOM tree, it is removed from its original position and added to its target position.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="753fa-107">참조</span><span class="sxs-lookup"><span data-stu-id="753fa-107">See also</span></span>

- [<span data-ttu-id="753fa-108">XML DOM(문서 개체 모델)</span><span class="sxs-lookup"><span data-stu-id="753fa-108">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
