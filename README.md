import { Card, CardContent } from "@/components/ui/card";
import { Tabs, TabsList, TabsTrigger, TabsContent } from "@/components/ui/tabs";
import { Progress } from "@/components/ui/progress";
import { Button } from "@/components/ui/button";

export default function Dashboard() {
  return (
    <div className="p-6 grid gap-6">

      {/* 상단 요약 영역 */}
      <div className="grid md:grid-cols-5 gap-4">
        <Card><CardContent className="p-4">🎯 전체 출석률: 92%</CardContent></Card>
        <Card><CardContent className="p-4">🧠 예습 퀴즈 참여율: 85%</CardContent></Card>
        <Card><CardContent className="p-4">📊 자기평가 제출률: 78%</CardContent></Card>
        <Card><CardContent className="p-4">✅ 퀴즈 평균 정답률: 81%</CardContent></Card>
        <Card><CardContent className="p-4">📂 성과물 제출: 12건 (최근: 6/20)</CardContent></Card>
      </div>

      {/* 수업 목록 카드 */}
      <div className="grid md:grid-cols-2 gap-4">
        {["AI프로그래밍", "컴퓨터 조직론", "자료구조"].map(course => (
          <Card key={course}>
            <CardContent className="p-4 space-y-2">
              <div className="text-lg font-bold">{course} – 홍길동 교수 / 화 3-4교시</div>
              <div>7주차 / 총 15주차</div>
              <div className="text-sm">✔️ 예습 참여 / ✔️ 자기평가 / 🧠 퀴즈: 8점 / 📎 성과물 제출 완료</div>
              <Button className="mt-2">수업 상세 보기</Button>
            </CardContent>
          </Card>
        ))}
      </div>

      {/* 할 일 알림 */}
      <Card>
        <CardContent className="p-4">
          <h3 className="font-semibold text-lg mb-2">이번 주 할 일</h3>
          <ul className="list-disc pl-5 space-y-1 text-sm">
            <li>AI프로그래밍 – 예습퀴즈 미참여 (7주차)</li>
            <li>컴퓨터 조직론 – 자기평가 미제출 (6주차)</li>
            <li>자료구조 – 성과물 등록 마감 (오늘)</li>
          </ul>
        </CardContent>
      </Card>

      {/* 개인 역량 성장 */}
      <Card>
        <CardContent className="p-4">
          <h3 className="font-semibold text-lg mb-2">나의 성취 추이</h3>
          <div className="space-y-2 text-sm">
            <div>문제해결력: +12%</div>
            <Progress value={82} />
            <div>구조적 사고: +8%</div>
            <Progress value={68} />
            <div>SW기초지식: +9%</div>
            <Progress value={74} />
            <div className="text-xs mt-2 text-muted-foreground">🧭 AI 분석 결과: 문제해결력 우수 / 구조적 사고 보완 필요</div>
          </div>
        </CardContent>
      </Card>

      {/* 비교 인사이트 */}
      <Card>
        <CardContent className="p-4">
          <h3 className="font-semibold text-lg mb-2">비교 인사이트</h3>
          <ul className="list-disc pl-5 space-y-1 text-sm">
            <li>예습 퀴즈 정답률: 평균보다 ▲ 높음</li>
            <li>자기평가 결과 분포: 평균 수준</li>
            <li>주차별 성장 수준: 평균보다 ▼ 낮은 주차 있음 (5~6주차)</li>
          </ul>
        </CardContent>
      </Card>

      {/* AI 맞춤 제안 */}
      <Card>
        <CardContent className="p-4">
          <h3 className="font-semibold text-lg mb-2">AI 맞춤 제안</h3>
          <ul className="list-disc pl-5 space-y-1 text-sm">
            <li>“AI프로그래밍” 5주차 복습 추천</li>
            <li>문제해결력 보완 퀴즈 다시 풀기</li>
            <li>자주 틀린 문제 집중 리뷰</li>
          </ul>
        </CardContent>
      </Card>

    </div>
  );
}
