# option_valuation
- '17.11.10~'17.12.14동안 진행된 11월물 코스피 지수옵션의 델타 헤징 및 그릭스 가치 평가 프로젝트 수행 내역을 기록

## Black-Scholes Equation
- Black Scholes Formula
    -  <img src="https://latex.codecogs.com/svg.latex?\Large&space;\cfrac{{\partial}f}{{\partial}t}+rS\cfrac{{\partial}f}{{\partial}S}+\cfrac{1}{2}{\sigma^2}{S^2}\cfrac{{\partial}^2f}{{\partial}S^2}=rf">
- Call Option
    - <img src="https://latex.codecogs.com/svg.latex?\Large&space;C=max(S-K,0)"></center>
    - <img src="https://latex.codecogs.com/svg.latex?\Large&space;C(S,K,r,\sigma,t)\,=\,S\cdot{N(d_1)}-K{\cdot}e^{-r(T-t)}{\cdot}N(d_2)"/>
- Put Call Parity
    - <img src="https://latex.codecogs.com/svg.latex?\Large&space;C+Ke^{-rt}=P+S"/>
- Put Option
    - <img src="https://latex.codecogs.com/svg.latex?\Large&space;P=max(K-S,0)"/>
    - <img src="https://latex.codecogs.com/svg.latex?\Large&space;P(S,K,r,\sigma,t)\,=\,K{\cdot}e^{-r(T-t)}{\cdot}N(-d_2)-S\cdot{N(-d_1)}"/>

- Where
    - <img src="https://latex.codecogs.com/svg.latex?\Large&space;d_1=\cfrac{ln{\frac{S}{K}+(r+0.5\sigma^2)(T-t)}}{\sigma\sqrt{T-t}}"/>
    - <img src="https://latex.codecogs.com/svg.latex?\Large&space;d_2=d_1-\sigma\sqrt{T-t}"/>
    - <img src="https://latex.codecogs.com/svg.latex?\Large&space;N(x)=\int_{-\infty}^{x}\cfrac{e^{-\frac{1}{2}y^2}}{\sqrt{2\pi}}dy"/>

## Greeks
- Delta
    - <img src="https://latex.codecogs.com/svg.latex?\Large&space;\Delta_c=N(d_1)>0,\quad\Delta_p=-N(-d_1)<0"/>
- Gamma
    - <img src="https://latex.codecogs.com/svg.latex?\Large&space;\Gamma_c=\cfrac{{\partial}^2C}{{\partial}S^2}=N^{\prime}(d_1)\cfrac{{\partial}d_1}{{\partial}S}=\cfrac{N^{\prime}(d_1)}{S\sigma\sqrt{T-t}}=\cfrac{{\partial}^2P}{{\partial}S^2}=\Gamma_p"/>
- Theta
    - <img src="https://latex.codecogs.com/svg.latex?\Large&space;\Theta_c=\cfrac{{\partial}C}{{\partial}t}=-\cfrac{S{\sigma}N^{\prime}(d_1)}{2\sqrt{T-t}}-r{\cdot}Ke^{-r(T-t)}N(d_2)<0"/>
    - <img src="https://latex.codecogs.com/svg.latex?\Large&space;\Theta_p=\cfrac{{\partial}P}{{\partial}t}=-\cfrac{S{\sigma}N^{\prime}(d_1)}{2\sqrt{T-t}}+r{\cdot}Ke^{-r(T-t)}N(-d_2)"/>
- Vega
    - <img src="https://latex.codecogs.com/svg.latex?\Large&space;\nu_c=\cfrac{{\partial}C}{{\partial}\sigma}=S\sqrt{T-t}N(d_1)=\cfrac{{\partial}P}{{\partial}\sigma}=\nu_p>0"/>
- Rho
    - <img src="https://latex.codecogs.com/svg.latex?\Large&space;\rho_c=\cfrac{{\partial}C}{{\partial}r}=(T-t)K^{-r(T-t)}N(d_2)>0"/>
    - <img src="https://latex.codecogs.com/svg.latex?\Large&space;\rho_p=\cfrac{{\partial}P}{{\partial}r}=-(T-t)K^{-r(T-t)}N(-d_2)<0"/>
