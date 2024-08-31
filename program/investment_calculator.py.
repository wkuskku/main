import tkinter as tk
from tkinter import messagebox

# 투자 비중과 수익률을 기반으로 각 투자자가 가져가는 수익을 계산하는 함수
def calculate_returns(investments, profit):
    total_investment = sum(investments)
    returns = [investment / total_investment * profit for investment in investments]
    return returns

# 결과를 GUI에서 보여주기 위한 함수
def show_results():
    try:
        # 투자 비중과 총 수익 금액 입력
        investments = [
            float(investment_entries[i].get())
            for i in range(4)
        ]
        total_profit = float(profit_entry.get())

        # 수익 계산
        returns = calculate_returns(investments, total_profit)

        # 결과 출력
        results_text = "\n".join(f"투자자 {i + 1}: {int(return_amount)} 원" for i, return_amount in enumerate(returns))
        messagebox.showinfo("결과", f"각 투자자가 가져갈 수익 금액:\n{results_text}")

    except ValueError:
        messagebox.showerror("입력 오류", "모든 입력 필드는 숫자여야 합니다.")

# GUI 설정
root = tk.Tk()
root.title("투자 수익 계산기")

# 투자 금액 입력 필드
investment_labels = [tk.Label(root, text=f"투자자 {i + 1}의 투자 금액:") for i in range(4)]
investment_entries = [tk.Entry(root) for _ in range(4)]

for i in range(4):
    investment_labels[i].grid(row=i, column=0, padx=10, pady=5, sticky='e')
    investment_entries[i].grid(row=i, column=1, padx=10, pady=5)

# 총 수익 금액 입력 필드
profit_label = tk.Label(root, text="총 수익 금액:")
profit_label.grid(row=4, column=0, padx=10, pady=5, sticky='e')

profit_entry = tk.Entry(root)
profit_entry.grid(row=4, column=1, padx=10, pady=5)

# 결과 버튼
calculate_button = tk.Button(root, text="수익 계산", command=show_results)
calculate_button.grid(row=5, column=0, columnspan=2, pady=20)

# GUI 실행
root.mainloop()
