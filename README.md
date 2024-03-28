% Given data
Mp = [10000, 0, 0];
Tp = [0, 15000, 0];
Mv = [383, -50, 0];
Tv = [0, 0, 0];

% Calculations
C = (Mp + Tp) / 2;
R = Tp - Mp;
cross_product = cross(Mv, R);
n = cross_product / norm(cross_product);
cross_product1 = cross(n, R);
q = cross_product1 / norm(cross_product1);
cross_product2 = cross(n, Tv);
w = cross_product2 / norm(Tv);
w_dot_q = dot(w, q);
term1 = w - w_dot_q * q;
dot_product = dot(R, term1);
denominator = 2 * (1 - w_dot_q^2);
r = dot_product / denominator;
alpha = asin(norm(Tp - Mp))/(2 * norm(r));
l = (alpha * norm(Tp-Mp))/(sin(alpha));
v = norm(Tv - Mv);
t_go = l / v;

% Plotting
time = 1:1:10; % Example time steps, adjust as needed
variables = {'n', 'q', 'w', 'r', 't', 'l', 't_go'};
num_variables = numel(variables);

figure;
for i = 1:num_variables
    subplot(num_variables, 1, i);
    plot(time, eval(variables{i}));
    ylabel(variables{i});
    xlabel('Time');
    grid on;
end
sgtitle('Variables vs. Time');
- 👋 Hi, I’m @Sreerenjana
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
Sreerenjana/Sreerenjana is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
