---
title: 곡선 구성 및 그리기
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [Windows Forms], curves
- examples [Windows Forms], drawing curves
- curves [Windows Forms], drawing
ms.assetid: 76e92623-4130-4644-b867-faca58bdb3a2
ms.openlocfilehash: 4c1b0cc6c6f878569fcf0c392f1b6f9683ec8afc
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2019
ms.locfileid: "67506106"
---
# <a name="constructing-and-drawing-curves"></a><span data-ttu-id="d6452-102">곡선 구성 및 그리기</span><span class="sxs-lookup"><span data-stu-id="d6452-102">Constructing and Drawing Curves</span></span>
<span data-ttu-id="d6452-103">GDI + 여러 종류의 곡선을 지원 합니다: 타원, 원호를 카디 날 곡선 스플라인 및 3 차원 곡선 스플라인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6452-103">GDI+ supports several types of curves: ellipses, arcs, cardinal splines, and Bézier splines.</span></span> <span data-ttu-id="d6452-104">타원의 경계 사각형; 정의한 호에는 시작 각도 및 스윕 각도에서 정의 되는 타원의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="d6452-104">An ellipse is defined by its bounding rectangle; an arc is a portion of an ellipse defined by a starting angle and a sweep angle.</span></span> <span data-ttu-id="d6452-105">카디널 스플라인 포인트와 장력 매개 변수 배열에 의해 정의 된-곡선 배열의 각 요소 원활 하 게 전달 되 고 장력 매개 변수 곡률 방식에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d6452-105">A cardinal spline is defined by an array of points and a tension parameter — the curve passes smoothly through each point in the array, and the tension parameter influences the way the curve bends.</span></span> <span data-ttu-id="d6452-106">두 개의 끝점과 곡선 제어 지점을 통과 하지 않으므로 두 개의 제어점 베 지 어 스플라인을 정의 되어 있지만 제어점 방향에 영향을 줄 및 다른 끝점에서 곡선 흐르면서 수정.</span><span class="sxs-lookup"><span data-stu-id="d6452-106">A Bézier spline is defined by two endpoints and two control points  the curve does not pass through the control points, but the control points influence the direction and bend as the curve goes from one endpoint to the other.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d6452-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="d6452-107">In This Section</span></span>  
 [<span data-ttu-id="d6452-108">방법: 카디널 스플라인 그리기</span><span class="sxs-lookup"><span data-stu-id="d6452-108">How to: Draw Cardinal Splines</span></span>](how-to-draw-cardinal-splines.md)  
 <span data-ttu-id="d6452-109">카디널 스플라인 및 그리는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6452-109">Describes cardinal splines and how to draw them.</span></span>  
  
 [<span data-ttu-id="d6452-110">방법: 단일 3 차원 곡선 스플라인 그리기</span><span class="sxs-lookup"><span data-stu-id="d6452-110">How to: Draw a Single Bézier Spline</span></span>](how-to-draw-a-single-bezier-spline.md)  
 <span data-ttu-id="d6452-111">베 지 어 스플라인 및 하나를 그리는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6452-111">Describes a Bézier spline and how to draw one.</span></span>  
  
 [<span data-ttu-id="d6452-112">방법: 일련의 3 차원 곡선 스플라인 그리기</span><span class="sxs-lookup"><span data-stu-id="d6452-112">How to: Draw a Sequence of Bézier Splines</span></span>](how-to-draw-a-sequence-of-bezier-splines.md)  
 <span data-ttu-id="d6452-113">시퀀스의 몇 가지 3 차원 곡선 스플라인 그리기 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6452-113">Explains how to draw several Bézier splines in sequence.</span></span>
